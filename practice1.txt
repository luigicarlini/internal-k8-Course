Exercise 1: Running the hello-world Container



-------------------------------------------------------------------------------------------
1. Enter the docker run command in a Bash terminal or PowerShell window. 
This instructs Docker to run a container called hello-world:


$ docker run hello-world

Your shell should return output similar to the following:
Unable to find image 'hello-world: latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete 
Digest: sha256:
8e3114318a995a1ee497790535e7b88365222a21771ae7e53687ad76563e8e76
Status: Downloaded newer image for hello-world:latest
Hello from Docker!
This message shows that your installation appears to be working 
correctly.
To generate this message, Docker took the following steps:
1. The Docker client contacted the Docker daemon.
2. The Docker daemon pulled the "hello-world" image from the 
Docker Hub.
 (amd64)
3. The Docker daemon created a new container from that image 
which runs the executable that produces the output you are 
currently reading.
4. The Docker daemon streamed that output to the Docker 
client, which sent it to your terminal.
To try something more ambitious, you can run an Ubuntu 
container with:
$ docker run -it ubuntu bash
Share images, automate workflows, and more with a free Docker ID:
https://hub.docker.com/
For more examples and ideas, visit:
https://docs.docker.com/get-started/

-------------------------------------------------------------------------------------------
2. Use the docker ps command to see what containers are running on your 
system. In your Bash or PowerShell terminal, type the following command:


$ docker ps


This will return output similar to the following:
CONTAINER ID IMAGE COMMAND CREATED  STATUS PORTS NAMES

The output of the docker ps command is empty because it only shows 
currently running containers by default. This is similar to the Linux/Unix ps
command, which only shows the running processes

-------------------------------------------------------------------------------------------
3. Use the docker ps -a command to display all the containers, even the 
stopped ones:


$ docker ps -a


In the output returned, you should see the hello-world container instance:
CONTAINER ID   IMAGE COMMAND        CREATED              STATUS PORTS NAMES
24c4ce56c904   hello-world "/hello" About a minute ago
 Exited (0) About a minute ago inspiring_moser
 
-------------------------------------------------------------------------------------------
4. You can query your system to see what container images Docker cached locally. 
Execute the docker images command to view the local cache:

$ docker images

The returned output should display the locally cached container images:
REPOSITORY  TAG    IMAGE ID     CREATED      SIZE
hello-world latest bf756fb1ae65 3 months ago 13.3kB 

-------------------------------------------------------------------------------------------
5. If you execute the same docker run command over again, then, for each 
docker run command a user inputs, a new container instance will be created.

$ docker run hello-world


You should see the following output:
Hello from Docker!
This message shows that your installation appears to be 
working correctly.
To generate this message, Docker took the following steps:
1. The Docker client contacted the Docker daemon.
2. The Docker daemon pulled the "hello-world" image from 
 the Docker Hub.
 (amd64)
3. The Docker daemon created a new container from that image 
 which runs the executable that produces the output you 
 are currently reading.
4. The Docker daemon streamed that output to the Docker client, 
 which sent it to your terminal.
To try something more ambitious, you can run an Ubuntu container 
with:
$ docker run -it ubuntu bash
Share images, automate workflows, and more with a free Docker ID:
https://hub.docker.com/
For more examples and ideas, visit:
https://docs.docker.com/get-started/


this time, Docker did not have to download the container image 
from Docker Hub again. This is because you now have that container image 
cached locally. Instead, Docker was able to directly run the container and 
display the output to the screen. 


-------------------------------------------------------------------------------------------

6. In your terminal, run the docker ps -a command again:
docker ps -a

CONTAINER ID   IMAGE        COMMAND CREATED         STATUS      PORTS          NAMES
e86277ca07f1   hello-world "/hello" 2 minutes ago   Exited (0)  2 minutes ago  awesome_euclid
24c4ce56c904   hello-world "/hello" 20 minutes ago  Exited (0)  20 minutes ago inspiring_moser

You now have a second instance of this container showing in your output. Each 
time you execute the docker run command, Docker will create a new instance 
of that container with its attributes and data. You can run as many instances of 
a container as your system resources will allow.

-------------------------------------------------------------------------------------------

7. Check the base image again by executing the docker images command 
once more:
$ docker images

The returned output will show the single base image that Docker created two 
running instances from:

REPOSITORY   TAG    IMAGE ID     CREATED      SIZE
hello-world  latest bf756fb1ae65 3 months ago 13.3kB





 



