# Redis deployment - Multi Cluster

## Pre-requisites

Skupper installed and linked on two openshift clusters

##  Deploy 2 Redis nodes on cluster1

oc apply -f redis-0.yaml
skupper expose deployment skupper-redis-server-0 --port 6379,26379 

oc apply -f redis-1.yaml
skupper expose deployment skupper-redis-server-1 --port 6379,26379 

## Deploy 3 Redis nodes on cluster2

oc apply -f redis-2.yaml
skupper expose deployment skupper-redis-server-2 --port 6379,26379 

oc apply -f redis-3.yaml
skupper expose deployment skupper-redis-server-3 --port 6379,26379
 
oc apply -f redis-4.yaml
skupper expose deployment skupper-redis-server-4 --port 6379,26379 
