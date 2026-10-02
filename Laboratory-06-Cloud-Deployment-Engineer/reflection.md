# Laboratory 06 Reflection

This laboratory helped me understand how Docker Compose manages an application with multiple services. Instead of writing separate Docker commands for Nextcloud and MariaDB, I placed their settings in one YAML file. This made the deployment easier to follow because I could see the images, environment variables, and port mapping together. A single command started both services and created their shared network.

One challenge was learning how YAML indentation works. The structure depends on consistent spacing, so I had to check where each service and setting belonged. I also encountered a command issue because `docker compose` was unavailable in my environment. Using the working `docker-compose` command allowed me to continue.

Another problem occurred when I ran commands from the home directory instead of the project folder. Compose could not find its configuration file. Later, the temporary session reset, removing the folder and containers. I recreated the configuration, deployed the services again, and completed the teardown in the same session. These problems taught me to check my working directory and save evidence promptly.

Environment variables helped me understand how an application receives its database settings. Nextcloud used the database name, username, password, and service hostname defined in the configuration. These variables provide configuration, but placing passwords in YAML does not make them secure.

Seeing both containers marked `Up` and opening the Nextcloud setup page made the deployment process clearer to me. I did not complete administrator setup, so my evidence demonstrates container deployment and access to the installation page.

Compared with my initial understanding of cloud computing, I now see it as more than storing files online. It also involves configuring services, connecting components, checking their status, and managing their lifecycle. I still need practice, but I am becoming more comfortable interpreting terminal output and troubleshooting errors.
