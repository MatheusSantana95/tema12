Name: Matheus Arruda Ferreira de Santana.

### Prerequisites (Install the latest git package, docker and packer)

#### Install Latest Git Package

- Check if you have git on your machine. To check, first type the key combination Ctrl + Alt + T and execute the command: `git --version`;
- If nothing appears after you execute the above command, install git on your machine. To do that, on the terminal, type the command `sudo apt install git-all`;
- Now, check the install of git by running: `git --version`;
- You need to clone this repository.

#### Install Docker

- To install docker, go to the terminal and type the following commands:
- `sudo apt-get update`
- `sudo apt-get install docker-ce docker-ce-cli containerd.io`
- Now, verify if docker is correctly installed by running "Hello-world" image typing the command: sudo docker run hello-world; If the following message appears, it means that docker installation appears to be working correctly.
```
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```
To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

 ##### Post-Installations

 **Manage Docker as a non-root user:**

- First, you need to create a docker group. Go to the terminal and run: `sudo groupadd docker`;
- Add a user to the docker group by running: `sudo usermod -aG docker $USER`;
- Now, Log out and log back your machine.
- After that, back to the terminal and run the command: `newgrp docker` ;
- Now try to run a docker command without sudo by running: `docker run hello-world`. If a informational message appears, means that it works.

#### Create a Dockerhub account:

After that, you need to create a Dockerhub account. To do that, please click [here](https://hub.docker.com).
Then, create your public repository.

#### Install Packer

- To install packer, on the terminal enter the command: `sudo apt install packer`;
- Now, check the install of git by running: `packer --version`.

Packer Homework
===============

1. Create a packaer config file for backing a docker image of your go microservice.

### How to use the calculator microservice? 

- Type the key combination Ctrl + Alt + T, go to the folder "tema-10" and execute the command: `packer build packer.json`;
- To use the microservice, type the command `docker run -p 8080:8080 {Your_Public_Dockerhub_Repository}:calculator`.
- This application is on the port: 8080. You can do the sum, subtract, multiply and division opeations accessing the endpoint as below:

```
http://localhost:8080/calc/sum/$a/$b 
http://localhost:8080/calc/sub/$a/$b 
http://localhost:8080/calc/mul/$a/$b 
http://localhost:8080/calc/div/$a/$b
```

Note: The paremeters $a and $b is where you´ll put the desired numbers to do the desired operation.

- To access the historic, you can access the endpoint: `http://localhost:8080/calc/history`

- To stop your go microservice first type the command: `docker ps`;
- Copy the container id; 
- Then type the command: `docker stop {YOUR_CONTAINER_ID}`.