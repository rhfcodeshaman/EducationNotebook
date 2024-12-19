#note
# Subject Overview
**Overview**:
- 3rd Party Images
- Building Images
- Container Registries
- Running COntainers
- Container Security
- Docker CLI
- Dev Experience
- Deploying Containers
## 3rd Party Images
### Databases
[Containerized Database Documentation](https://docs.docker.com/guides/databases/)
- Using a local containerized database offers flexibility and ease of setup, letting you mirror production environments closely without the overhead of traditional database installations.
- Most popular database systems have an image on Docker Hub
- Example to run a database container using CLI. `-e` flag sets environment variables.
```
docker run --name my-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=mydb -d mysql:latest
```
- To access the shell of a containerized database, you will need to use the `docker exec` command. `-it` ensures the terminal you're accessing is interactive so you can actually type commands into it. `bash` is the command to run inside the container to open up a bash shell that lets you interact with the container's file system and installed apps.
```
docker exec -it my-mysql bash
```
- Once you've accessed the container's terminal, you can run any tools available in that container, to include interaction with the database.

- To connect to a containerized database form your host machine, you have to map a port inside the container to a port on your host machine. This ensures the database is accessible via the host machine's network.
```
docker run -p 3307:3306 --name my-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=mydb -d mysql:latest
```

- To connect a containerized app to a containerized database, you must place both the database and the app on the same Docker network.
```
docker network create my-network

docker run --name my-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=mydb --network my-network -d mysql:latest

docker run --name my-phpmyadmin -d --network my-network -p 8080:80 -e PMA_HOST=my-mysql phpmyadmin
```

- Then verify that the containers can communicate.
- Make sure the database's data is persistent with a Docker Volume or bind mount.

### Interactive Test Environments
[Dev Environment Documentation](https://docs.docker.com/desktop/features/dev-environments/create-dev-env/)
