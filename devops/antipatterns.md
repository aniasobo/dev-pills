# Database use antipatterns to avoid

## 1. Databases as message queues

Sending messages from one server to another using a database - BAD

Use case: 3 servers, each has clients connected to it, they communicate with each other via the single database with inserts. The database can't contact the servers, so the servers have to call the db at specific intervals.

Polling the db frequently like this means lots of read operations on the db, which can overload it easily.

Extending the intervals impacts the performace on the client so user experience is worse.

A db is usually optimised for reading or for writing, but usually not both. So sending a lot of read operations to a write db will result in a lot of locking, dead locks etc.

CRUD operations - dbs are rarely optimised for both read and write CRUD operations to be fast.

Scalability - the db will become less performant as load increases with more servers added.

Using `message queues` - but not the dbs, rather specialised message queues/brokers - solves this problem.

### Drawbacks of using message queues:

- they're not good for smaller systems where the db could actually handle the load of the servers reading from it
- when there's not a lot of messaging happening, the read and write operations are unnecessarily long
- requires time to set up and not every system is large enough to be worth this effort
-
