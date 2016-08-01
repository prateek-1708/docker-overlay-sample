### Consul
# Run consul ins dkr_host_3 for swarm KV store.

docker run -d -p "8500:8500" -h "consul" progrium/consul -server -bootstrap

Initialise a docker swarm by running the init command like so 
```
	docker swarm init --advertise-addr <ip address>
```

the node where this command becomes the swarm master / manager. This command also spits out a join sample command.





    Swarm initialized: current node (556ntfiyb752kd5rm0tn36183) is now a manager.

To add a worker to this swarm, run the following command:
    docker swarm join \
    --token SWMTKN-1-2tqlvaramizb7jaib4rhvehlj851yyshfcftif2eqbtn5hcnbx-71p5jfo357qjl15fc86fauyes \
    192.168.56.103:2377

To add a manager to this swarm, run the following command:
    docker swarm join \
    --token SWMTKN-1-2tqlvaramizb7jaib4rhvehlj851yyshfcftif2eqbtn5hcnbx-dhdebjvb1605kp20x19k0bbku \
    192.168.56.103:2377



docker run -itd nginx

docker run -it busybox wget -O- http://dkr-host-1
