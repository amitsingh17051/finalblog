---
title: "Docker Image for Laravel, PHP, MySQL, and Nginx Server"
description: "Docker Image for Laravel, PHP, MySQL, and Nginx Server"
publishDate: "01 Jan 2024"
tags: ["docker"]
draft: false
---



This document provides instructions for creating a Docker image that includes Laravel, PHP, MySQL, and Nginx server. The Docker image is built using the provided Dockerfiles and follows a specific set of steps to configure the environment.

Dockerfile 1
------------

The first Dockerfile sets up a container with PHP, MySQL, Nginx, and Laravel installed. It uses the official PHP base image \`php:7.4-fpm\` as the starting point. The following steps are performed:

1\. The working directory in the container is set to \`/var/www/html\`.

2\. System dependencies like curl, libpng, libonig, libxml2, zip, unzip, nginx, and supervisor are installed using the \`apt-get\` command.

3\. The cache is cleared to optimize the container’s size.

4\. PHP extensions required by Laravel (pdo\_mysql, mbstring, exif, pcntl, bcmath, gd) are installed using \`docker-php-ext-install\`.

5\. Composer is installed to manage the Laravel application’s dependencies.

6\. The source code of the Laravel application is copied into the container’s working directory.

7\. File permissions for the Laravel application’s storage and cache folders are set.

8\. Nginx is configured by copying a custom Nginx configuration file.

9\. Supervisor is configured by copying a custom supervisor configuration file.

10\. Port 80 is exposed to allow external access.

11\. The supervisor process is run to manage the Nginx and PHP-FPM processes.

Dockerfile 2
------------

The second Dockerfile defines the Docker image specifically for the Laravel application, PHP, MySQL, and Nginx server. Here’s a breakdown of the steps:

1\. The base image is set as the official PHP image with PHP-FPM (\`php:7.4-fpm\`).

2\. The working directory in the container is set to \`/var/www/html\`.

3\. Necessary dependencies like git, curl, libpng, libonig, libxml2, zip, and unzip are installed using \`apt-get\`.

4\. PHP extensions required by Laravel are installed using \`docker-php-ext-install\`.

5\. Composer is installed to manage the Laravel application’s dependencies.

6\. The Laravel application files are copied into the container.

7\. Permissions are set for the Laravel storage and bootstrap directories.

8\. Application dependencies are installed using Composer.

9\. The Laravel application key is generated.

10\. Port 9000 is exposed for PHP-FPM.

11\. PHP-FPM is started.

Building and Running the Docker Image
-------------------------------------

To build the Docker image for Laravel, PHP, MySQL, and Nginx server, follow these steps:

1\. Install Docker: If Docker is not already installed on your system, download and install it from the official Docker website ([https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)).

2\. Create a new directory for your project: Open your terminal and create a new directory for your project. For example, you can use the command \`mkdir docker-laravel\`.

3\. Navigate to the project directory: Change to the project directory using the command \`cd docker-laravel\`.

4\. Create a Dockerfile: Create a new file named \`Dockerfile\` in the project directory. Copy the contents of one of the provided Dockerfiles into this file, depending on your requirements.

5\. Build the Docker image: Run the following command in the terminal to build the Docker image:

```
docker build -t laravel-app
```

This command builds a Docker image using the Dockerfile in the current directory and tags it as “laravel-app”.

6\. Run the Docker container: Execute the following command in the terminal to run the Docker container:

docker run -d -p 80:80 - name laravel-container laravel-appshe

This command runs a Docker container in detached mode (-d) with port mapping (-p) from the host’s port 80 to the container’s port 80. The container is named “laravel-container” and uses the “laravel-app” image.

7\. Verify the container is running: Use the following command to list all running Docker containers:

docker ps

Make sure the “laravel-container” is listed and has the status “Up”.

Now you should have a Docker container running with Laravel, PHP, MySQL, and Nginx server. You can access the application by visiting [http://localhost](http://localhost) in your web browser.

Verifying the Docker Container
------------------------------

To verify that the Laravel, PHP, MySQL, and Nginx server are running correctly in the Docker container, follow these steps:

1\. Install Docker: If Docker is not already installed on your system, download and install it from the official Docker website ([https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)).

2\. Build the Docker image: Navigate to the directory containing the Dockerfile and execute the following command to build the Docker image:
```
docker build -t laravel-app .
```
3\. Run the Docker container: Start the Docker container using the following command:

docker run -d -p 80:80 - name laravel-container laravel-app

4\. Verify the container is running: Use the

