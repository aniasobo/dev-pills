## Good tools for APIs:  

* [JengaAPI](https://www.jengaapi.io/)
* [Postman](https://www.getpostman.com/)
* [Insomnia REST client](https://insomnia.rest/)

[also here >](api/../../api/clients.md)
---

# Intro to RESTful APIs

REST - a set of conventions for writing routes

### Resources

Web = network of resources; resource = data stored somewhere  

**a resource is a "//noun// stored //location//"**

### Representations  

Representation = route for a user to take to a resource (ex. stuff that ties the URL to an action)

**NOUN/plural/id**  

Example RESTful representations:

```
GET /bookmarks/1
GET /users/217
GET /image.jpg
GET /bookmarks/1
GET /index.html
```

**Web applications are state machines and REST defines their interface**

RESTful routing exposes the nature of your web app - a state machine capable of a certain variety of states.  

Movements between those states are determined by user interactions, called **state transitions**:  

state | state transition | RESTful route  
--- | --- | ---
Having 35 bookmarks | returns 35 bookmarks | `GET /bookmarks`
Adding a bookmark | transitions the machine to a new state, returns 36 bookmarks | `POST /bookmarks`
Deleting a bookmark | transitions the machine to a new state of 35 bookmarks, returns 35 bookmarks | `DELETE /bookmarks/4`

#### states & state transitions:

- Having 35 bookmarks (state)
- Adding a bookmark (state transition)
- Having 36 bookmarks (state)
- Deleting a bookmark (state transition)
- Having 35 bookmarks (state)

### Other resources:

Extracted from [this README](https://learn.co/lessons/sinatra-restful-routes-readme)

For the initialize class, [refer to this](https://itnext.io/removing-argument-order-dependencies-c5e2482ba208)
