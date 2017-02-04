# docker-haproxy

### Description
Load balancer for 3 web servers.  This image was created to deploy a load
balancer in a Docker container, to load balance a web server Docker service
deployed in a Docker Swarm.

### Docker Instructions

##### Pull the Docker image from Docker Hub:
```bash
docker pull xwin/haproxy
```
##### Create a container from the image and run it:
```bash
docker run -d --name haproxy -p 8080:80 xwin/haproxy
```

### Configure haproxy
Edit the haproxy.cfg file.

##### Build the container
```bash
docker build -t haproxy .
```

##### Test the configuration file
```bash
docker run -it --rm --name haproxy-syntax-check haproxy -c -f /usr/local/etc/haproxy/haproxy.cfg
```

##### Run the container
```bash
docker run -d --name haproxy -p 8080:80 haproxy
```

### Test the load balancer
```bash
curl localhost:8080
```
