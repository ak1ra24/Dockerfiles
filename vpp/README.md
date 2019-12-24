## Setup
```
docker run --name vppxx -it --privileged -d akiranet24/vpp:19.04
docker exec -it vppxx nohup /usr/bin/vpp -c /etc/vpp/startup.conf
```
