# Standard Package Layout <!-- omit in toc -->

[SOURCE](https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1)

- [1. Root package is for domain types](#1-root-package-is-for-domain-types)
- [2. Group subpackages by dependency](#2-group-subpackages-by-dependency)
- [3. Use a shared mock subpackage](#3-use-a-shared-mock-subpackage)
- [4. Main package ties together dependencies](#4-main-package-ties-together-dependencies)

---

## 1. Root package is for domain types

Logical, high-level language that describes how data and process interact - this is your domain. 

Root package only contains simple data types like `User` struct for holding user data or a `UserService` interface for fetching or saving user data.

```
package myapp

type User struct {
	ID      int
	Name    string
	Address Address
}

type UserService interface {
	User(id int) (*User, error)
	Users() ([]*User, error)
	CreateUser(u *User) error
	DeleteUser(id int) error
}
```

The root package should not depend on any other package in your application. No services included in the root package should call external services or save to databases.

## 2. Group subpackages by dependency

External dependencies belong in subpackages. Subpackages are an adapter between your domain and your implementation.

Example: your `UserService` depends on postgres so introduce a `postgres` subpackage that provides a `postgres.UserService` implementation:

```
package postgres

import (
	"database/sql"

	"github.com/benbjohnson/myapp"
	_ "github.com/lib/pq"
)

// UserService represents a PostgreSQL implementation of myapp.UserService.
type UserService struct {
	DB *sql.DB
}

// User returns a user for a given id.
func (s *UserService) User(id int) (*myapp.User, error) {
	var u myapp.User
	row := db.QueryRow(`SELECT id, name FROM users WHERE id = $1`, id)
	if row.Scan(&u.ID, &u.Name); err != nil {
		return nil, err
	}
	return &u, nil
}

// implement remaining myapp.UserService interface...
```

This way the pg is isolated and can be easily tested or migrated to a different db, or used as pluggable architecture to use with other dbs.

You can also layer it this way, for example wrap it in a cache implementation:

```
package myapp

// UserCache wraps a UserService to provide an in-memory cache.
type UserCache struct {
        cache   map[int]*User
        service UserService
}

// NewUserCache returns a new read-through cache for service.
func NewUserCache(service UserService) *UserCache {
        return &UserCache{
                cache: make(map[int]*User),
                service: service,
        }
}

// User returns a user for a given id.
// Returns the cached instance if available.
func (c *UserCache) User(id int) (*User, error) {
	// Check the local cache first.
        if u := c.cache[id]]; u != nil {
                return u, nil
        }

	// Otherwise fetch from the underlying service.
        u, err := c.service.User(id)
        if err != nil {
        	return nil, err
        } else if u != nil {
        	c.cache[id] = u
        }
        return u, err
}
```

Good example of this architecture: the `io.Reader` domain type in the standard library.

Wrap external dependencies with a logical domain type - for example if using Stripe, wrap it in a `TransactionService` so that your dependencies communicate solely through our common domain language.

You can use the same rule for isolating standard library dependencies - for example your `net/http` package:

```
package http

import (
        "net/http"
        
        "github.com/benbjohnson/myapp"
)

type Handler struct {
        UserService myapp.UserService
}

func (h *Handler) ServeHTTP(w http.ResponseWriter, r *http.Request) {
        // handle request
}
```

This way your `http.Handler` acts as an adapter between your domain and the HTTP protocol.

## 3. Use a shared mock subpackage

When your dependencies are isolated from each other by your domain interfaces, you can use those connection points to inject mock implementations.

You can write the mocks yourself or use something like `GoMock`.

## 4. Main package ties together dependencies

Since an app might use many binaries, use the Go convention of placing the `main` package as subdirectory of the `cmd` package. Layout:

```
myapp/
    cmd/
        myapp/          // the server binary
            main.go
        myappctl/       // the client binary for managing the server from terminal
            main.go
```

The `main` package is what gets to choose which dependencies to inject to which objects.

The `main` package stays small because all it does is wiring up the pieces:

```
package main

import (
	"log"
	"os"
	
	"github.com/benbjohnson/myapp"
	"github.com/benbjohnson/myapp/postgres"
	"github.com/benbjohnson/myapp/http"
)

func main() {
	// Connect to database.
	db, err := postgres.Open(os.Getenv("DB"))
	if err != nil {
		log.Fatal(err)
	}
	defer db.Close()

	// Create services.
	us := &postgres.UserService{DB: db}

	// Attach to HTTP handler.
	var h http.Handler
	h.UserService = us
	
	// start http server...
}
```

The `main` package is also an adapter connecting the terminal to your domain.