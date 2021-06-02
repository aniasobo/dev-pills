# Master - Slave Architecture

## Advantages:

- multiple backups of the data
- read operations can be easily scaled up - run data from master to a slave that then performs some data analytics or operations
- very scalable
- good for sharding - horizontal partitioning - of the data with multiple masters, each of which has a backup slave

`Single Point of Failure` - one way to solve it is with Horizontal Distribution

Lots of servers - one db? the db is a SPF - created copies of the db in physically different locations

### Synchronous or asynchronous copying of the db data:

- asynchronous: a transaction that passes on the master db may be lost if the master db crashes before slaves are updated
- synchronous replication: every command made on master is send to slave(s) to keep consistent state; write operations on slaves are only allowed to come from master, never servers; if the master goes down, one of the slaves could become a master (or there could be multiple masters) with read-write operations coming in from servers

only masters have write permissions

`Split Brain Problem` - when both dbs assume they are masters but they can't communicate so the data becomes inconsistent - solved by adding a third. This leads to -> `Distributed Consensus`: multiple nodes agree on a value (multiple versions of the db is one way to solve it, by Postgres; SAGA - a long transaction that at any point can fail and then has to be rolled back - it's only committed if all of it is successful)
