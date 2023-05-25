# mongo-replica-docker-compose-example
an example replication set in MongoDB is a group of mongod processes that maintain the same data set. Replica sets provide redundancy and high availability, and are the basis for all production deployments.


The primary node receives all write operations. A replica set can have only one primary capable of confirming writes with { w: "majority" } write concern; although in some circumstances, another mongod instance may transiently believe itself to also be primary. [1] The primary records all changes to its data sets in its operation log, i.e. oplog. For more information on primary node operation, see Replica Set Primary.

![image](https://github.com/savinnsk/mongo-replica-docker-compose-example/assets/54680650/78bda2cc-b93e-4c3e-8bac-57f156c6bf1d)


The secondaries replicate the primary's oplog and apply the operations to their data sets such that the secondaries' data sets reflect the primary's data set. If the primary is unavailable, an eligible secondary will hold an election to elect itself the new primary. For more information on secondary members, see Replica Set Secondary Members.


![image](https://github.com/savinnsk/mongo-replica-docker-compose-example/assets/54680650/23f6bf07-cef3-45b8-9bc8-eb6cb4e80442)


An arbiter will always be an arbiter whereas a primary may step down and become a secondary and a secondary may become the primary during an election.

![image](https://github.com/savinnsk/mongo-replica-docker-compose-example/assets/54680650/d14465cd-31ef-44d7-a981-73bfc756ed87)
