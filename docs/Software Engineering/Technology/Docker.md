---
share: true
---
## Connecting from Container to host
One problem I faced was to connect to the host from a container. (It was because of a live logging application)

I achieved the desired result by doing adding the extra_hosts section in my compose file:
```yaml
services:
	example:
	...
		extra_hosts:
		  - logserver.local: host-gateway
```

With this I can call `logserver.local` inside of my container and it gets routed to the localhost.

If you want to configure it so that host-gateway points to a specific IP address you can configure it in the `/etc/docker/daemon.json`
```json
{ "host-gateway-ip": "<desiredIP>" }
```

This can be especially useful if you install docker without docker-desktop on WSL. Then you can route your host-gateway to the virtual network-interface connecting to windows.


## Synchronizing Timezone of Host with Container
Docker containers are by default in the timezone ETC/UTC, if you need to have it synchronized to the local machine then you will find multiple options on the internet:

### 1. Set the TZ variable
In a `docker-compose.yml`:
```yml
services:
# ...
# Container Definition in docker.compose.yaml
  environments:
    - TZ=Europe/Berlin

```

As single command:
```bash
docker run -rm -e TZ=Europe/Berlin debian:latest date
```

| Pro                  | Contra                                                                         |
| -------------------- | ------------------------------------------------------------------------------ |
| Works for most cases | Does not work if timezone needs to be updated without recreating the container |
| Easy to set up       |                                                                                |
 
### 2. Bind the system time files to the container
In a `docker-compose.yml`
```yml
services:
# ...
# Container Definition in docker.compose.yaml
  volumes:
    - /etc/timezone:/etc/timezone:ro
    - /etc/localtime:/etc/localtime:ro
```


| Pro                                          | Contra                            |
| -------------------------------------------- | --------------------------------- |
| Timezone is set correctly                    | localtime does not work correctly |
| Time is synchronized to the host continously |                                   |
### 3. Combination
This solution combines the two concepts and sets the TZ Variable on every start of the container.
For that we need to add a script to the Dockerfile.
```
ENTRYPOINT ["/bin/bash", "startupScript.sh"]
```

In the script we set the TZ and then startup the application:
```shell
#!/bin/bash  
if timezone=$(cat /etc/timezone 2>/dev/null); then  
    export TZ="$timezone"  
    echo "Using Timezone $timezone"  
fi  
./Application # this is the command to run your application
```

If we do it like this, then every time we restart the container the timezone is synchronized with the host.