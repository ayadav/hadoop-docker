#Apache Hadoop 2.7.2 Docker image

[![DockerPulls](https://img.shields.io/docker/pulls/kimptoc/hadoop-docker.svg)](https://registry.hub.docker.com/u/kimptoc/hadoop-docker/)
[![DockerStars](https://img.shields.io/docker/stars/kimptoc/hadoop-docker.svg)](https://registry.hub.docker.com/u/kimptoc/hadoop-docker/)

Fork of the great sequenceiq build - https://github.com/sequenceiq/hadoop-docker - providing access to 2.7.2

# Build the image

If you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t sequenceiq/hadoop-docker:2.7.2 .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull sequenceiq/hadoop-docker:2.7.2
```

# Start a container

In order to use the Docker image you have just build or pulled use:

**Make sure that SELinux is disabled on the host. If you are using boot2docker you don't need to do anything.**

```
docker run -it sequenceiq/hadoop-docker:2.7.2 /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.2.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

## Hadoop native libraries, build, Bintray, etc

Not provided in this build - its a pure java version, so not as fast as it could be :)

