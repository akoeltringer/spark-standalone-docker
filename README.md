# Spark Standalone Docker Container

This repo is about creating a Docker container with Apache Spark, as vanilla as possible. The intended use is deployment as standalone cluster.

## Example usage:

Launch master container:

```
docker run --rm \
           --name spark-master \
           --publish 8080:8080 \
           akoeltringer/spark-standalone master
```

Launch slave container:

```
docker run --rm \
           --name spark-worker1 \
           --link spark-master \
           akoeltringer/spark-standalone slave "spark://spark-master:7077"
```
