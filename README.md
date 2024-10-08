# Docker-installation
Docker installation and configuration
1 - before installation check WSL
	cmd => WSL --status

2 - then install Ubuntu (restart system)
	cmd => WSL install

3 - install Docker desktop

4 - check docker version
	cmd => docker version

5 - run docker hello world
	cmd => docker run hello-world

 6 - create image command
 	cmd =>  docker build -t servicedotjar .
     To check images in docker command
        cmd => docker image ls
7 - run docker image
	cmd => docker run -p 9100:8080 servicedotjar
 	In this setup:
	. 8080 is the internal port used by Netty (inside the Docker container).
	. 9100 is the external port on your host (Windows) machine.

	Override the port directly in the docker run command
	if you have application-docker.properties profile then tell about active profile
	docker run -p 9100:9100 -e "SPRING_PROFILES_ACTIVE=docker" -e "SERVER_PORT=9100" wis-service-gateway

8 - if there is application-docker.properties then activate docker profile with command
 	cmd => ENV SPRING_PROFILES_ACTIVE=docker

9 - To up docker compose file
	docker-compose up --build

	

