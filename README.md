Ways to test:
=============

There are two ways of doing this:

* provision 3 or more nodes using docker-machine create -d virtualbox <docker_host_name>

Let's start by provision three docker machines on which we will run our swarm cluster.
```	
docker-machine create -d virtualbox dkr-swarm-node-1
docker-machine create -d virtualbox dkr-swarm-node-2
docker-machine create -d virtualbox dkr-swarm-node-3
```
now lets start our swarm. Point your docker engine at the first node. It will become the swarm manager. You point your engine at first node
```
eval $(docker-machine env dkr-swarm-node-1)
```
like so, kick start the swarm cluster on this node
```
docker swarm init --advertise-addr $(docker-machine ip dkr-swarm-node-1) --listen-addr $(docker-machine ip dkr-swarm-node-1):2377
```
On execution above command will generate swarm tokens for other nodes to join. Copy and paste the bit for joining nodes. We are not interested in joining another master as we are just evaluting swarm althoug, in ideal world you will create redundant manager nodes for your cluster.

So once you copy the "join nodes bit" point your docker engine to node 2 and 3 respectively and execute the join command.

```
eval $(docker-machine env dkr-swarm-node-2)
docker swarm join \
    --token SWMTKN-1-652grzkvrpc87q2dt3miwvnny71eu9sdguhz07xykcdpcjjaku-5dqfb6gu9c7iaoph68sjpfmtv \
    192.168.99.100:2377

eval $(docker-machine env dkr-swarm-node-3)
docker swarm join \
    --token SWMTKN-1-652grzkvrpc87q2dt3miwvnny71eu9sdguhz07xykcdpcjjaku-5dqfb6gu9c7iaoph68sjpfmtv \
    192.168.99.100:2377
```
NOTE: the above token will be different for you. 


Networking Fun:
===============
```
docker network create --driver overlay swarm_test
```

Swarm Master:
=============

Initialise a docker swarm by running the init command like so 
```
docker swarm init --advertise-addr $(docker-machine ip dkr-swarm-node-1) --listen-addr $(docker-machine ip dkr-swarm-node-1)
```

the node where this command becomes the swarm master / manager. This command also spits out a join sample command.



* provision 3 or more nodes using vagrant boxes and do the docker shenanigins on them.


## Vagrant Way

There is a very basic vagrant file in the repo. All you need is to install virtual box and vagrant on your system. Once installed 

```
Vagrant up
```
three boxes in one swift command. Once  

====== In Progress.
