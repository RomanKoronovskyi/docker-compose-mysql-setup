# docker-compose-setup
## Branch: phpMyAdmin+MariaDB

## Project Description
This project demonstrates the use of **Docker Compose** to set up an environment with a **MariaDB** database and a **phpMyAdmin** web interface.  
Custom Docker images include the `iputils-ping` package for network testing inside containers.

## Project Structure

dockercompose/
├─ Dockerfile.frontend # phpMyAdmin with ping
├─ Dockerfile.mydb # MariaDB with ping
├─ docker-compose.yml # services, networks, and volumes configuration
├─ README.md # documentation

## Implemented Features

- Custom **phpMyAdmin** image with `iputils-ping`.
- Custom **MariaDB** image with `iputils-ping`.
- **Volume** `dockercompose-mydb` for database data persistence.
- **Healthcheck** to verify database availability (`mysqladmin ping`).
- **Custom network** `dockercompose-frontend` for container communication.
- Automatic creation of the `mydb` database via MariaDB environment variables.

## Running the Project

1. Ensure Docker and Docker Compose are installed.
2. Build images and start containers:

```bash
docker compose up -d
```

---

## Branch: Wordpress+MySQL

## Project Description
This project demonstrates the use of **Docker Compose** to set up an environment with a **MySQL** database and a **Wordpress** web interface.  

## Project Structure

dockercompose/
├─ Dockerfile.wordpress # Wordpress 
├─ docker-compose.yml # services, networks, and volumes configuration
├─ wp-config.php # Wordpress configuration

## Implemented Features

- Custom **Wordpress** image used for permissions configuration and copying wp-config.php.
- **Volumes** `mysql` and `wordpress`.
- **Custom network** `bridge-network` for container communication.
- Automatic creation of the database via MariaDB environment variables.

## Running the Project

1. Ensure Docker and Docker Compose are installed.
2. Build images and start containers:

```bash
docker compose up -d
```

---

## Branch: Spring+MySQL

## Project Description
This project implements the Spring Petclinic application, utilizing a multi-stage build Dockerfile and an isolated MySQL database container.

## Project Structure

dockercompose/
├─ Dockerfile # Spring
├─ docker-compose.yml # services, networks, and volumes configuration

## Implemented Features

- Uses a builder image (hlebsur/pet_clinic_not_full) and a lightweight runtime image (eclipse-temurin:17-jre-jammy) for a minimized final container size.
- Dedicated Database: Uses a custom MySQL image (hlebsur/mysql:8) for the backend.
- Healthcheck: Database availability is confirmed by the container's built-in healthcheck, ensuring applications connect reliably.
- Service Dependency: Petclinic is configured with depends_on: mysqlserver, ensuring the DB starts first.
- Volume Persistence: Database data (mysql_data) and configuration (mysql_config) are saved using named volumes.
- Custom Network: Both containers communicate over the isolated petclinic network.
- Access: Application is exposed on host port 8080.

## Running the Project

1. Ensure Docker and Docker Compose are installed.
2. Build images and start containers:

```bash
docker compose up -d
```



