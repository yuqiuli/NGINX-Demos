# Go webapp that returns the hostname, IP address, the request URI, the local time and the system user running the app in the server.

The image is uploaded to Docker Hub -- https://hub.docker.com/r/nginxdemos/go-hello/.

How to run:
```
$ docker run -P -d nginxdemos/go-hello
```

Now, assuming we found out the IP address and the port that mapped to port 8080 on the container, we can make a request to the webapp and get the result below: 
```
$ curl <ip>:<port>
Server address: 172.17.0.2
Server name: 730fae3d41f7
Date: 2019-12-19T18:18:50Z
URI: /tea
Current System User: username=nginx uid=101
```

The example was created to be used as simple backend for various load balancing demos.