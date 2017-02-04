Description
Load balancer for 3 web servers.

Build the container:
$ docker build -t haproxy .

Test the configuration file:
$ docker run -it --rm --name haproxy-syntax-check haproxy -c -f /usr/local/etc/haproxy/haproxy.cfg

Run the container:
$ docker run -d --name haproxy -p 8080:80 haproxy
