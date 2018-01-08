# portainer-ssh
Portainer with ability to pull template from private git repositories.

## Deployment
The code uses swarm specific functions like secrets. It should work without swarm mode but you have to bind mount all secrets.

```bash
docker stack deploy -c docker-compose.yml portainer
```

### With Traefik Proxy
The config is prepared to run in conjunction with a traefik proxy. To use it simply uncomment the external network interface and adapt the name of the interface accordingly. So the same with `- "traefik.docker.network=FULL NETWORK INTERFACE NAME"`.

After a few seconds, portainer should be accessible from `http://localhost:9000` or the given domain, if you are using a proxy.

## Templates
To use the example template, login to portainer, go to `Settings`, activate `Use Cusom Templates` and use the following url: `http://internal.templates/templates.json`, then `save settings`. At `Templates` you should find the Test template.