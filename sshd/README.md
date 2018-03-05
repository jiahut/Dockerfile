# dockerfiles-centos-ssh

# Building & Running

Copy the sources to your docker host and build the container:

	# docker build --rm -t <username>/ssh:centos7 .

To run:

	# docker run --name ssh --privileged -d -p 2202:22 <username>/ssh:centos7

Get the port that the container is listening on:

```
# docker ps
CONTAINER ID        IMAGE                 COMMAND                   CREATED             STATUS              PORTS                   NAMES
931cdbc9d968        me/ssh:centos       "/sbin/init"             2 days ago          Up 2 days           0.0.0.0:2202->22/tcp       ssh
```

To test, use the port that was just located:

	# ssh -p xxxx user@localhost 

