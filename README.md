# docker-compose-mysql-setup
Docker Compose: phpMyAdmin + MariaDB

## Project Description
This project demonstrates the use of **Docker Compose** to set up an environment with a **MariaDB** database and a **phpMyAdmin** web interface.  
Custom Docker images include the `iputils-ping` package for network testing inside containers.

---

## Project Structure

dockercompose/
├─ Dockerfile.frontend # phpMyAdmin with ping
├─ Dockerfile.mydb # MariaDB with ping
├─ docker-compose.yml # services, networks, and volumes configuration
├─ README.md # documentation

---

## Implemented Features

- Custom **phpMyAdmin** image with `iputils-ping`.
- Custom **MariaDB** image with `iputils-ping`.
- **Volume** `dockercompose-mydb` for database data persistence.
- **Healthcheck** to verify database availability (`mysqladmin ping`).
- **Custom network** `dockercompose-frontend` for container communication.
- Automatic creation of the `mydb` database via MariaDB environment variables.

---

## Running the Project

1. Ensure Docker and Docker Compose are installed.
2. Build images and start containers:

```bash
docker compose up -d


