# hbase-ersatz
hbase replication service


## What is this service?

This service runs the HBASE RPC server wrapped in a Jetty server. This service is registered as a replication sink on the source cluster. We can register custom event handlers that consume the events and write to the destination. 


## Where is the code man??

For now, I have it at https://bitbucket.org/ravimagham/hbase-ersatz

## Show me a high level view of how it works

 ![Overall Picture](https://github.com/mravi/hbase-ersatz/blob/master/Ersatz%20Service%20High%20Level.png)
