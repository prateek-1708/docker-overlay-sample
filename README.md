### Consul
# Run consul ins dkr_host_3 for swarm KV store.

docker run -d -p "8500:8500" -h "consul" progrium/consul -server -bootstrap