
# spark

## docker-compose example

To create a simplistic standalone cluster with [docker-compose](http://docs.docker.com/compose):

    docker-compose up

The SparkUI will be running at `http://${YOUR_DOCKER_HOST}:8080` with one worker listed. The logs will be pushed to the elasticsearch container.
Kibana will be accessible at `http://${YOUR_DOCKER_HOST}:5601`

## license

MIT
