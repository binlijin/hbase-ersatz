# hbase-ersatz
hbase replication service

## What is this service?

This service runs the HBASE RPC server wrapped in a Jetty server. This service is registered as a replication sink on the source cluster. We can register custom event handlers that consume the events and write to the destination. 

## Show me a high level view of how it works

 


## Packaging

* mvn clean package


## Deployment

* Start the service on a node using
```bash
  java -jar target/ersatz-hbase-server.jar server path/to/config.yml
```

* At HBase shell, run the following commands.

```bash
hbase> create 'test', {NAME => 'd', REPLICATION_SCOPE => '1'}
hbase> add_peer '1', "zk:2181:/hbase-slave/events"'
hbase> put 'test', 'r1', 'd', 'value'
```

## TODO
* A lot , lot has to be done to make it production quality. Ex. capturing metrics on data received. 
* re-design the consumers to use SPI for better manageability.
* needs lot of tests to be written.
