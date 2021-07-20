# Go best practices

From [Go idioms](https://youtu.be/MzTcsI6tn-0)

What code goes in which package?

Code patterns and conventions in the standard library

Unwritten conventions

## Packages

Code organisation in Go to increase your testability and funcitonality: 

- package naming
- package organisation 

One influences the other. 

Packages contain code that has a single purpose. Organise package under a parent if the funcitonalities have different implementation - children inherit the interface. 

Name - describes the purpose. It's easy to guess what a package does by the name. Names should be short. Parent package can be more descriptive ( see the `encoding` package as example).

### Application packages

Organisation of executable applications - slightly different in that the executable command is important (??)

Problems with testing are usually caused by incorrect organisation of the application package.

Application code should be easy to understand, easy to refactor and easy for someone else to maintain.

Application ties the single-purpose libraries together to create a tool or service - the resulting tool will have a much larger scope.

**Organising the libraries you use in your app:**

- Domain Types - the types that model your business functionality and objects
- Services - are packgaes that operate on or with your domain types

The package that contains your domain types (e.g. Product) should also define the interfaces between your domain types and the rest of the world. The interfaces define the things you want to do with your domain types, eg: `ProductService`, `SupplpierService`, `AuthenticationService`, `EmployeeStorage`, `RoleStorage` - what are the things I need to be able to do with a `Product`/`Employee`? - those should be in the root psckage of the repo.

The domain type package/root package should not have any external dependencies - it's a roadmap for the application. It should describe the types and behaviours.

Implementations - in subdirectories, in separate packages, organised by dependency.

**Dependencies:**

- external data sources
- transportation logic: http, RPC
- you should have one package per dependency
  - simplifies testing
  - easy substitution/replacement
  - no circular dependencies

## Naming conventions

Think how you name your types, functions and package names to make your code easy to understand and maintainable.

Package name should be __short__ and __clear__ based on its funcitonality, or describing the implementation of an external dependency. Avoid catchall names like `util` or `helpers` - this is a sign that you might be missing an interface somewhere; package functionality should be __single purpose__ and that's reflected in the name!

Example: `util.ConvertOtherToThing()` should probably be refactored to a `Thinger` interface.

Catchall names are also where problems with testing and circular dependencies tend to happen.

**Variable naming**

- go uses `camelCase`
- single letter far for indexes, starts with `i`, followed by `j`, `k` etc
- short but descriptive - the further away from declaration it is used, the more descriptive the name should be!
- use two letters to represent a slice of a collection, e.g.: `var tt []*Thing`
- in a loop/range, use the single letter, e.g.: `for i, t := range tt {}`

**Functions and methods**

- don't repeat the package name in package-level function name - the package name already reflects the purpose!
- there are no getters or setters in Go - so no `getCustomer` or `setCustomer` functions

**Interfaces**

- if the interface only has one function, append `-er`: `type Stringer interface{ String() string }`
- if it has more than one function, use a name that represents funcitonality without -er, like `CustomerStorage`

**Source Code**

- separate code inside package into logical concerns
- if the package deals with many types, keep the logic for each type in its own source file:
  - package: `postgres` - `orders.go`, `suppliers.go`, `products.go`
- in the package that defines your domain objects, define the types and interfaces for each obj in the same source file:
  - package: `inventory` - `orders.go` containing `Orders type and OrderStorage interface`
- comments should be full sentences `// An Order represents an order form a customer.` - makes your comments look like documentation

Use `goimports` to manage your imports and they'll always be in __canonical order__: standard lib first, external next, each in alphabetical order.

Avoid the `else` clause, especially in error handling, e.g.:

```
if err != nil {
    // error handling
    return // or continue etc
}
```

The `else` is implied 👆.


