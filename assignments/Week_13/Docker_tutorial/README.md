<p align = "center" draggable=”false” ><img src="https://user-images.githubusercontent.com/37101144/161836199-fdb0219d-0361-4988-bf26-48b0fad160a3.png"
     width="200px"
     height="auto"/>
</p>


# <h1 align="center" id="heading">Hands on Docker Tutorial</h1>


### Docker Lab Playground

#### In the first part of this Lab, we will play with docker commands.

1. Create a docker login (free)
https://hub.docker.com/

2. Login to Docker Playground with your docker credentials
https://labs.play-with-docker.com/

3. In the page that opens up, click `Add Instance` on the left panel. You are now ready to enter commands in the terminal.
![image](https://user-images.githubusercontent.com/37101144/166613197-5838cc5b-e9a0-4de7-a25b-0093bd72f03d.png)


This command gives you the version of docker
``` bash
  docker -v
```

This command pulls up an existing docker image and runs it
``` bash
  docker run -dp 8000:8000 docker/getting-started:pwd
```

This command lists the docker container images
``` bash
  docker images
```

This command shows the exposed ports/containers
``` bash
  docker ps
```

Whenever a port is exposed, the port number will be visible on the top (as shown below, see 80 in purple next to OPEN PORT Button]. If you click on the number 80, the localhost version of the docker image will open up.

![image](https://user-images.githubusercontent.com/37101144/166613213-76bd39df-5614-4bcc-ab85-459a02faca9f.png)


Notice the CONTAINER ID from the output of `docker ps`

Now to close the docker application type the following commands

``` bash
docker image rm -f docker/getting-started:pwd
docker container stop <CONTAINER ID>
```

This will close the application!

Hit Close session to end your Docker playground session!
