# crossfire-all-in-one
A Docker Swarm solution which contains: Trojan, VMess/{WSS,H2}. ALL IN ONE.

## Usage
```
./configure <UUID> <host>
docker stack deploy -c crossfire.yml crossfire
```

You may need to run `docker swarm init` before.
Make sure ports 80 and 443 is available and Docker can bind them.

### Tips
You can run these commands in your local computer.
Just run
```
export DOCKER_HOST=ssh://<user>@<host>:<port>
```
before commands aforementioned.

## What includes

- Trojan: `https://<host>:8443`
- VMess transported via
  - WSS: `https://<host>:443/filesync/[UUID]/v2ray/ws/vmess`
  - H2: `https://<host>:443/filesync/[UUID]/v2ray/h2/vmess`
