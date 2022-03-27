# Index <!-- omit in toc -->

- [Systems design interview - concepts to know](#systems-design-interview---concepts-to-know)
- [Tools](#tools)
- [Basics](#basics)
- [Load balancers](#load-balancers)

## Systems design interview - concepts to know 

- [ ] Vertical vs horizontal scaling
- [ ] CAP theorem
- [ ] ACID vs BASE
- [ ] Partitioning/Sharding
- [ ] Consistent Hashing
- [ ] Optimistic vs pessimistic locking
- [ ] Strong vs eventual consistency
- [x] [RelationalDB vs NoSQL](../devops/sql-nosql.md)
- [ ] Types of NoSQL:
  - [ ] Key value
  - [ ] Wide column
  - [ ] Document-based
  - [ ] Graph-based
- [ ] Caching
- [ ] Data center/racks/hosts
- [ ] CPU/memory/Hard drives/Network bandwidth
- [ ] Random vs sequential read/writes to disk
- [ ] HTTP vs http2 vs WebSocket
- [ ] TCP/IP model
- [ ] ipv4 vs ipv6
- [ ] TCP vs UDP
- [ ] DNS lookup
- [ ] Http & TLS
- [ ] Public key infrastructure and certificate authority(CA)
- [ ] Symmetric vs asymmetric encryption
- [x] [Load Balancer](#load-balancers)
- [ ] CDNs & Edges
- [ ] Bloom filters and Count-Min sketch
- [ ] Paxos
- [ ] Leader election
- [ ] Design patterns and Object-oriented design
- [ ] Virtual machines and containers
- [x] [Pub-sub architecture](../devops/publisher-subscriber.md)
- [ ] MapReduce
- [ ] Multithreading, locks, synchronization, CAS(compare and set)

## Tools

- [x] [Cassandra](../devops/sql-nosql.md#cassandra-cluster-nosql-database)
- [ ] MongoDB/Couchbase
- [ ] Mysql
- [ ] Memcached
- [ ] Redis
- [ ] Zookeeper
- [ ] Kafka
- [ ] NGINX
- [ ] HAProxy
- [ ] Solr, Elastic search
- [ ] Amazon S3
- [ ] Docker, Kubernetes, Mesos
- [ ] Hadoop/Spark and HDFS

[SOURCE](https://www.youtube.com/watch?v=UzLMhqg3_Wc&list=PLrmLmBdmIlps7GJJWW9I7N0P0rB0C3eY2) plus more links

## Basics

- [Numbers everyone should know](https://web.archive.org/web/20210207060829/https://everythingisdata.wordpress.com/2009/10/17/numbers-everyone-should-know/) - also accompanying [keynote from google](https://web.archive.org/web/20210308032622/https://www.cs.cornell.edu/projects/ladis2009/talks/dean-keynote-ladis2009.pdf)

## Load balancers

[SOURCE](https://dev.to/bmf_san/implement-a-load-balancer-in-golang-8gj) and also [THIS](https://kasvith.me/posts/lets-create-a-simple-lb-go/)

There are two main types of load balancers.

An L7 load balancer that load balances at the application layer and an L4 load balancer that load balances at the transport layer.

In addition to load balancing, the load balancer has the functions of persistence (session maintenance) and health check.

### Type of load balancing <!-- omit in toc -->

There are different types of load balancing, **static** and **dynamic**.

A typical static method is Round Robin, which distributes requests evenly.

A typical dynamic method is Least Connection, which distributes requests to the server with the least number of unprocessed requests.

### Types of persistence <!-- omit in toc -->

Persistence is a function for maintaining a session between multiple servers to which the load balancer is distributed.

There are two main methods, **Source address affinity persistence** and **Cookie persistence**.

Source address affinity persistence is a method to fix the destination server by looking at the source IP address.

Cookie persistence is a method that issues a cookie to maintain a session, looks at the cookie, and fixes the server to which it is distributed.

### Health check type <!-- omit in toc -->

Health check is a function that the load balancer checks the operating status of the distribution destination server.

An active health check method that checks the health of the load balancer to the server to which it is distributed, and a method that monitors the response to requests from clients.

Active checks can be classified into L3 check, L4 check, and L7 check depending on the protocol used.