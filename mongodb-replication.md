##Goal
High Availability and Fault tolerance 
##Solution
Replication
##Replication
* _Replication is a way of keeping identical copies of your data on multiple servers._
* _Replication keeps your application running and your data safe, even if something happens to one or more of your servers._
* _Replication provide redundancy and high availability._
* _Replication itself works by way of a special `capped collection` called the `oplog`._
* _This collection keeps a rolling record of all operations applied to the `primary`._
* _Secondary members then replicate this log by applying the operations to themselves in an asynchronous process._
* _Under normal operation,`secondary` members reflect writes within one second of the primary. However, various exceptional situations may cause secondaries to lag behind further._
* _All members send heartbeats (pings) to all other members in the set and can import operations to the local oplog from any other member in the set._

##Setting up a replica set
**With MongoDB, you set up replication by creating a replica set.**
* A replica set is a group of servers with one primary and multiplesecondaries, servers that keep copies of the primary’s data.
* If the primary crashes, the secondaries can elect a new primary from amongst themselves.
* Secondaries may fall behind the primary and not have the most current writes, so secondaries will refuse read requests by default to prevent applications from accidentally reading stale data. Thus, if you attempt to query a secondary, you’ll get an error that it’s not primary.
* To allow queries on the secondary, we set an “I’m okay with reading from secondaries” flag, like so 
*  `> conn.setSlaveOk()`
* on secondry mongo shell.we can use `rs.slaveOk()`
* We have to set read preference settings 
* The secondary does not accept the write. The secondary will only perform writes that it gets through replication, not from clients.

##configuring a Replica Set:

