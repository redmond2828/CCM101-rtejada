# Mission Reflection

This activity helped me understand the difference between deploying a Docker container and preparing a virtual machine. A VM needs a separate guest operating system, which requires installation, configuration, and booting. A container uses the host kernel and starts an application from an existing image. Container startup is generally faster, although downloading the image can add time. In this activity, I pulled the Nginx image and launched the web server without manually installing Nginx inside a guest operating system.

I learned why port mapping is important. In `-p 8080:80`, port 8080 belongs to the host, while port 80 belongs to the container. This mapping allowed my request to `http://localhost:8080` to reach Nginx. The HTML response containing “Welcome to nginx!” provided evidence that the web server was accessible through the published port.

The lifecycle commands also showed that stopping and removing a container are different actions. After `docker stop`, the container remained visible through `docker ps -a` with an exited status. After `docker rm`, it disappeared from the list. Removing a container deletes its writable layer, so data stored only there is lost. Named volumes and bind-mounted files persist separately, making storage planning important.

Containerization can help developers and IT operations teams work together by using the same application image across environments. This reduces problems caused by different dependencies and configurations. Developers can package the application, while operations teams manage deployment, networking, security, and storage. Both teams still need clear communication and shared responsibility.

My GitHub portfolio is developing from introductory cloud concepts into practical technical demonstrations. Lab 4 adds Docker commands, deployment evidence, and lifecycle documentation. I also corrected a duplicated folder while organizing the screenshots. This reminded me that accurate documentation and a clear repository structure are important parts of presenting technical work.

## Reference

Docker. (n.d.). *Storage.*
https://docs.docker.com/engine/storage/
