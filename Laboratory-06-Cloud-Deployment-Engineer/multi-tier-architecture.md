# Two-Tier Architecture

## Definition

In this deployment, a two-tier architecture separates the application into a web/application tier and a database tier. Nextcloud handles the user interface and application logic, while MariaDB stores structured application data.

## The Web/Application Tier

The Nextcloud container serves the web interface and handles HTTP requests. It processes application tasks and communicates with the database to read and update information.

Users access this tier through host port 8080, which maps to port 80 inside the container.

## The Database Tier

The MariaDB container stores structured data such as user accounts, settings, and file metadata. Uploaded file contents are stored separately in Nextcloud's file storage.

The Nextcloud application connects to this tier using the database service name.

## Why Separate Them?

Separate containers allow the application and database to be configured, updated, and troubleshot independently. Each container has a clear responsibility, making the deployment easier to maintain. The database can communicate with the application through the internal Docker network without publishing its port to the host.

## Reference

Docker. (n.d.). *Multi-container applications.*
https://docs.docker.com/get-started/docker-concepts/running-containers/multi-container-applications/
