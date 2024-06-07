# Hadoop

1. Make a working directory, somewhere

```
mkdir running-hadoop
cd running-hadoop
```

2. Clone the big-data-europe fork for commodity hardware

```
(base) mailesakamoto@Mailes-MacBook-Pro-2 running-hadoop % git clone https://github.com/big-data-europe/docker-hadoop
```

3. Test Docker 


```
(base) mailesakamoto@Mailes-MacBook-Pro-2 running-hadoop % docker run hello-world
```

4. Change version - we need to use docker-compose-v2, but the docker-compose command will look for an unversioned file.

```
(base) mailesakamoto@Mailes-MacBook-Pro-2 eu % mv docker-compose.yml docker-compose-v1.yml
mv docker-compose-v3.yml docker-compose.yml
```


5. Bring the Hadoop containers up (took me 81.6s). I had previously pulled other hadoop images though so your time may vary.

```
docker-compose up -d
```

```(base)
mailesakamoto@Mailes-MacBook-Pro-2 docker-hadoop % docker ps
CONTAINER ID   IMAGE                                                    COMMAND                  CREATED          STATUS                      PORTS                                            NAMES
9dc2a2083417   bde2020/hadoop-namenode:2.0.0-hadoop3.2.1-java8          "/entrypoint.sh /run…"   32 minutes ago   Up 32 minutes (unhealthy)   0.0.0.0:9000->9000/tcp, 0.0.0.0:9870->9870/tcp   namenode
de6783e36c1f   bde2020/hadoop-historyserver:2.0.0-hadoop3.2.1-java8     "/entrypoint.sh /run…"   32 minutes ago   Up 7 minutes (unhealthy)    8188/tcp                                         historyserver
3db4d1951377   bde2020/hadoop-datanode:2.0.0-hadoop3.2.1-java8          "/entrypoint.sh /run…"   32 minutes ago   Up 7 minutes (unhealthy)    9864/tcp                                         datanode
c92dde4438d3   bde2020/hadoop-nodemanager:2.0.0-hadoop3.2.1-java8       "/entrypoint.sh /run…"   32 minutes ago   Up 7 minutes (unhealthy)    8042/tcp                                         nodemanager
0ad6dd4d184a   bde2020/hadoop-resourcemanager:2.0.0-hadoop3.2.1-java8   "/entrypoint.sh /run…"   32 minutes ago   Up 7 minutes (unhealthy)    8088/tcp                                         resourcemanager
```

This is very humbling but this is where my Hadoop stopped working. I got several error codes while trying to go different routes or re-start and then I did not really know what other directions to take it. I reached out to classmates but was unable to get Hadoop up and running. :( 
