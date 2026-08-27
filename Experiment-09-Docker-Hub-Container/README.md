# Ex.No: 09-Docker-Hub-Container

# Run a Container from Docker Hub

## AIM

To write a program to run a container from Docker hub.

## ALGORITHM

1. Open a terminal.
2. Run `docker -h` to view Docker CLI help.
3. Run the first Ubuntu container using `docker container run -it ubuntu top`.
4. Docker pulls `ubuntu:latest` from Docker Hub if it is not locally available.
5. Verify that the container is running.
6. Open another terminal and use `docker container ls` to obtain the container ID.
7. Enter the container using `docker container exec -it <CONTAINER_ID> bash`.
8. Run `ps -ef` inside the container to inspect processes.
9. Exit the container.
10. Run an Nginx container using `docker container run --detach --publish 8080:80 --name nginx nginx`.
11. Open localhost:8080 to view the Nginx welcome page.
12. Run a MongoDB container using `docker container run --detach --publish 8081:27017 --name mongo mongo:4.4`.
13. Check the running containers using `docker container ls`.
14. Stop the containers.
15. Use `docker system prune` to remove stopped containers and other unused resources.

## PROGRAM / CODE

```text
# Ubuntu
docker container run -it ubuntu top

# Enter a running container
docker container exec -it <CONTAINER_ID> bash

# Nginx
docker container run --detach --publish 8080:80 --name nginx nginx

# MongoDB
docker container run --detach --publish 8081:27017 --name mongo mongo:4.4

# Check containers
docker container ls
```

## SAMPLE INPUT

```text
Docker Hub images: ubuntu, nginx, mongo:4.4
```

## SAMPLE OUTPUT

```text
Ubuntu runs with `top`; Nginx is accessible on localhost:8080 and displays the Nginx welcome page; MongoDB runs with port 27017 published on localhost:8081; `docker container ls` lists the running containers.
```

## RESULT

Thus, the write program to run a container from Docker Hub executed and verified successfully.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
