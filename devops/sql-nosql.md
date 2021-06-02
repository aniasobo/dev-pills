# SQL vs noSQL databases

## No SQL

- blobs of JSON data, nested into objects instead of joining tables
- use when:
  - your data is a block
  - updates are few and
  - you're ok with retrieving the entire block each time
  - you need something Write-optimised
  - you want aggregation of the data for analytics, metrics etc

**ADVANTAGES**

- schema can be easily changed
- built for scale
- great for aggregation of data, for example to get the average values etc (great for analytics), make it easy to find metrics

**DISADVANTAGES**

- not good for updates: every update is a delete + insert; this means the data is more likely to be inconsistent between nodes
- lack of consistency means you can't have transactions the same way you can with SQL - big reason why financial services don't use those dbs for their transactions
- not Read-optimised - every row will be read to retrieve the single piece of data, so the read times will be slower than with SQL
- no explicit information about relations
- joins of noSQL tables are very hard - they're all manual

## SQL

- tables with foreign keys to join in relevant data

**ADVANTAGES**

- Read-optimised: will only read the specific column you ask for
- easily malleable with all the different joins

**DISADVANTAGES**

## Cassandra cluster (NoSQL database)

- requests connect to nodes based on their id value
- keys/ids in noSQL don't always have to be numeric - can be uuid, name etc
- distributed consensus via Quorum - the way in which nodes related to particular query decide on the correct value of data; if the majority of the nodes within the RF value aggree on the state of data, it is taken as the source of truth (i.e. quorum)

FEATURES:

- load balancing
- redundancy/replication:
  - data guarantee
  - speed in reading
  - the next node (or nodes, depending on the value of your Replication Factor - RF) from the one chosen by the hash function in the load balancer will always have a copy of the data

LOG FILE:

- key-value pairs
- each request writes a new line
- stores data like a log
- fast retrieval
- all the data in the log is periodically dumped into an SST (Sorted String Table - sorted because the `key` is sorted)
- the data in the SST is immutable, so you eventually have multiple records for the same key with different timestamps, wherein comes:

COMPACTION:

- Cassandra merges data from different SSTs that is duplicate but has different timestamps
- tombstones timestamps of dead records

[SOURCE](https://www.youtube.com/watch?v=xQnIN9bW0og)
