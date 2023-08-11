# docker-bitcoind

## Setup
Prepare configuration for `bitcoind`
```sh
cp bitcoin.conf.sample bitcoin.conf
vim bitcoin.conf # Edit the configuration to fit your needs
```

Start container
```sh
docker-compose up -d
```

Access shell
```sh
# In host
$ docker ps
$ docker exec -it container_id bash
```

See logs
```sh
docker logs --tail 100 container_id
```
