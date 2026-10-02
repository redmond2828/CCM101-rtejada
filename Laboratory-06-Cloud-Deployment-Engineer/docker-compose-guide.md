# Docker Compose Deployment Guide

## Environment

This laboratory used KillerCoda Ubuntu 24.04 and Docker Compose version 1.29.2. The working command in this environment was `docker-compose`.

## 1. Create the Project Folder

```bash
mkdir -p ~/nextcloud-deployment
cd ~/nextcloud-deployment
nano docker-compose.yml
```

## 2. Define the Services

The following configuration defines the MariaDB database and Nextcloud application:

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - "8080:80"
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

Use spaces for YAML indentation. In nano, save with Ctrl+O, press Enter, and exit with Ctrl+X.

### What does the services block do?

The `services` block describes the containers that Compose manages. Each service specifies its image and configuration.

- `database` runs MariaDB 10.6. Its environment variables configure the initial database, database user, and passwords.
- `app` runs Nextcloud. Its environment variables supply the database connection settings.
- `8080:80` maps port 8080 on the Ubuntu host to port 80 inside the Nextcloud container.

### Why is MYSQL_HOST set to database?

Compose connects both services to a default network. Containers on that network can find each other using their service names.

`MYSQL_HOST=database` tells Nextcloud to use the MariaDB service named `database`. MariaDB does not need a published host port for this communication.

## 3. Validate and Deploy

Run these commands from the project folder:

```bash
docker-compose --version
docker-compose config
docker-compose up -d
docker-compose ps
```

`docker-compose config` checks and displays the configuration. `up -d` creates and starts the services in the background.

The status output showed both the application and database containers as `Up`.

![Running Nextcloud and MariaDB containers](screenshots/compose-deployment.png)

## 4. Open Nextcloud

Using KillerCoda's port access feature, I opened port 8080.

The Nextcloud setup page appeared with an “Autoconfig file detected” message. This confirmed that the web application was reachable and had detected its configuration. I did not create an administrator account or complete installation.

![Nextcloud setup page](screenshots/nextcloud-web.png)

## 5. Tear Down the Deployment

From the same project folder, run:

```bash
docker-compose down
docker-compose ps
```

The teardown stopped and removed both containers and removed the project's default network. The final status output contained no service entries.

This command does not remove volumes by default.

![Successful deployment teardown](screenshots/compose-teardown.png)

## docker run vs. docker-compose up -d

`docker run` creates and starts one container using options supplied on the command line.

`docker-compose up -d` reads the YAML file and starts the defined services together. Compose also manages their default network, making the application configuration easier to reuse.

## Troubleshooting Encountered

- The `docker compose` command was unavailable in the environment. I used the working `docker-compose` command.
- Running Compose outside the project folder produced a configuration-file error. The commands must run from the folder containing `docker-compose.yml`, or specify the file explicitly.
- After the temporary session reset, the project folder and containers were gone. I recreated the configuration and deployment, then completed the teardown in the same session.

## References

- [Docker Compose Networking](https://docs.docker.com/compose/how-tos/networking/)
- [Docker Compose Down](https://docs.docker.com/reference/cli/docker/compose/down/)
