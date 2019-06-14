# consul-docker

Consul Docker Compose file for Swarm

## Create Swarm Cluster

on node1:

```bash
docker swarm init --advertise-addr $ADVERTISE_IP
```
on node2, node3:

```bash
docker swarm join --token $TOKEN $ADVERTISE_IP:2377 
```

on node1:

```bash
docker node promote node1
docker node promote node2
docker node promote node3
```

## Create Swarm Network for Production: prod

```bash
docker network create --driver=overlay --attachable prod
```
