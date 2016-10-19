
# Spark and ELK in Docker

This Docker Cluster will be made up of :

* A Spark Cluster
    * Master Node 1
    * Worker Node 1     
    * Worker Node 2

* An ELK Cluster
    * Elastic Search Container
    * Logstash Container     
    * Kibana Container
    
Each nodes of the Spark Cluster push logs to the logstash instance, which parses them and writes the results in the Elastic instance. 
Logs can then be analysed accessing the Kibana UI.
        
## Running cluster

To create the clusters with [docker-compose](http://docs.docker.com/compose):

```
docker-compose up
```


## Submitting Spark Job

### Connecting to the Master
```
docker exec -it dockersparkelk_master_1 bash
```

### Submitting jar
```
 ./bin/spark-submit ...
```
The SparkUI will be running at `http://${YOUR_DOCKER_HOST}:8080`. The logs will be pushed to the elasticsearch container.

## Visualizing logs in Kibana

Kibana will be accessible at `http://${YOUR_DOCKER_HOST}:5601`
Some existing visualisations and dashboards can be found in ./kibana/objects.json and can be immported directly in Kibana.

## license

MIT
