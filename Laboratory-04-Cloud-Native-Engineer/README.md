
# Laboratory 04 - The Cloud-Native Engineer

## Mission Overview

This activity explores the differences between virtual machines and containers and demonstrates deploying an Nginx web server using Docker in the KillerCoda Ubuntu playground.

## Objectives

- Compare virtual machines and containers.
- Verify Docker installation and daemon availability.
- Pull and run the official Nginx image.
- Map a host port to a container port.
- Verify the web server using curl.
- Stop, inspect, and remove a container.
- Document commands and screenshots in GitHub.

## Docker Commands Executed

### Environment Verification

- `docker --version`
- `docker version`
- `docker info`
- `docker ps`

### Nginx Deployment

- `docker pull nginx:latest`
- `docker run -d --name lab4-nginx -p 8080:80 nginx:latest`
- `curl http://localhost:8080`

### Container Lifecycle

- `docker ps`
- `docker stop lab4-nginx`
- `docker ps`
- `docker ps -a`
- `docker rm lab4-nginx`
- `docker ps -a`

## Skills Learned

- Distinguishing VM architecture from container architecture.
- Checking Docker client and server availability.
- Downloading an image and creating a container.
- Running a container in detached mode.
- Publishing container port 80 through host port 8080.
- Checking an HTTP response using curl.
- Verifying the difference between stopped and removed containers.
- Organizing Markdown documentation and screenshot evidence.

## Challenges Encountered

I initially created a duplicate Lab 4 folder while setting up the screenshots directory. I corrected the structure by removing the misplaced placeholder and creating screenshots/.gitkeep inside the correct Lab 4 folder.

I also needed guidance on pasting commands into the browser terminal. After entering the commands, I successfully deployed Nginx, verified its welcome page, and stopped and removed the container.

## Documentation

- [VMs vs. Containers](virtualization-vs-containers.md)
- [Docker Deployment](docker-deployment.md)
- [Mission Reflection](reflection.md)

## Screenshot Evidence

### Docker Verification

![Docker verification](screenshots/docker-version.png)

### Nginx Running

![Nginx running](screenshots/nginx-running.png)

### Container Lifecycle

![Container lifecycle](screenshots/container-lifecycle.png)

## AI Assistance Disclosure

ChatGPT assisted with explanations, troubleshooting guidance, and documentation drafts. I executed the Docker commands and captured the screenshots myself.
