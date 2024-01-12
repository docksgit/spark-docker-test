Sources:
- Steps\
[Using Apache Spark Docker containers to run pyspark programs using spark-submit](https://medium.com/@mehmood9501/using-apache-spark-docker-containers-to-run-pyspark-programs-using-spark-submit-afd6da480e0f)
- Problem solving\
[Cannot docker-compose exec when container_name is set](https://github.com/docker/compose/issues/4706)


List of commands:
1. `docker-compose up -d`
2. `docker cp -L test.py spark-docker-test-spark-master-1:/opt/bitnami/spark/test.py`
3. `docker logs spark-docker-test-spark-master-1`
4. `docker-compose exec spark-master spark-submit --master spark://172.19.0.2:7077 test.py`

Info:
- project/directory name and container group name -> `spark-docker-test`
- container name -> `spark-docker-test-spark-master-1`
- service name -> `spark-master`

Remarks:
- `spark-docker-test-spark-master-1` in command 2 is a container name (look at "docker ps" command or Docker Desktop)
- `spark-master` in command 4 is a service name (look at docker-compose.yml)
- `spark://172.19.0.2:7077` in command 4 is spark master address where we have copied our py file into previously (find this address by command 3 or look at Docker Desktop > click spark-docker-test-spark-master-1 container)
