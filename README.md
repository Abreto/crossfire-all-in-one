# crossfire-all-in-one
A Docker Swarm solution which contains: Trojan, VMess/{WSS,H2}, SS/{WSS,H2}. ALL IN ONE.

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

- Trojan: `https://<host>:443`
- SS-libev with v2ray-plugin: `https://<host>:443/filesync/ss/v2ray-plugin`
- SS(v2ray implemention) transported via
  - WSS: `https://<host>:443/filesync/v2ray/ws/ss`
  - H2: `https://<host>:443/filesync/v2ray/h2/ss`
- VMess transported via
  - WSS: `https://<host>:443/filesync`
  - H2: `https://<host>:443/filesync/v2ray/h2/vmess`
