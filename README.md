# docker-bitcoind

## Setup
Prepare configuration for `bitcoind`
```sh
cp bitcoin.conf.sample bitcoin.conf
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
