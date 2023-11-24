# docker-bitcoind

Run bitcoind with tor on Docker.
- The base image is [mu373/docker-bitcoind-image](https://github.com/mu373/docker-bitcoind-image)
    - This is a fork of [kylemanna/docker-bitcoind](https://github.com/kylemanna/docker-bitcoind) with tor preinstalled.
- Works well with mempool running in separate containers: [mu373/docker-mempool](https://github.com/mu373/docker-mempool).

## Setup
Prepare configuration for `bitcoind`
```sh
cp docker-compose-template.yml docker-compose.yml
cp bitcoin.sample.conf bitcoin.conf
vim bitcoin.conf # Edit the configuration to fit your needs

# If you want to customize tor configs
cp torrc.d/custom-config torrc.d/my-custom-config
vim torrc.d/my-custom-config
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

# In the container
$ bitcoin-cli -netinfo 4  # Check that there is successful onion connection
```

See logs
```sh
docker logs --tail 100 container_id
```
