# docker-bitcoind

Run bitcoind on Docker.
- Base image is from [kylemanna/docker-bitcoind](https://github.com/kylemanna/docker-bitcoind).
- Works well with mempool running in separate containers: [mu373/docker-mempool](https://github.com/mu373/docker-mempool).

## Setup
Prepare configuration for `bitcoind`
```sh
cp docker-compose-template.yml docker-compose.yml
cp bitcoin.sample.conf bitcoin.conf
vim bitcoin.conf # Edit the configuration to fit your needs
```

Start the container
```sh
docker compose up -d
```

Access the shell inside the container
```sh
# In host
docker ps # Check container id
docker exec -it container_id bash
```

See logs
```sh
docker logs --tail 100 container_id
```
