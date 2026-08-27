# Ex.No: 08-Docker-First-Container

# Creating and Executing Your First Container Using Docker

## AIM

To write a program to Creating and Executing Your First Container Using Docker.

## ALGORITHM

1. Install Docker on the machine.
2. On Ubuntu, update packages using `sudo apt update`.
3. Install Docker using `sudo apt install docker.io`.
4. Verify Docker using `sudo docker run hello-world`.
5. Create a project directory.
6. Create `main.py`.
7. Create a `Dockerfile`.
8. Write the Python program that prints `Docker is magic!`.
9. Select the Python base image using `FROM python:latest`.
10. Copy `main.py` into the image using `COPY`.
11. Define the execution command using `CMD`.
12. Build the image using `docker build -t python-test .`.
13. Run the image using `docker run python-test`.
14. Verify the output.
15. Use Docker commands such as `docker image ls`, `docker ps -a`, `docker stop`, `docker rm`, and `docker logs` when required.

## PROGRAM / CODE

```text
# main.py
#!/usr/bin/env python3
print("Docker is magic!")

# Dockerfile
FROM python:latest
COPY main.py /
CMD [ "python", "./main.py" ]
```

## SAMPLE INPUT

```text
Run:
docker build -t python-test .
docker run python-test
```

## SAMPLE OUTPUT

```text
Docker is magic!
```

## RESULT

Thus, the Creating and Executing Your First Container Using Docker executed and verified successfully.

---

### Files

- `README.md` – Complete experiment record
- `screenshots/` – Place your actual lab screenshots here

> **Note:** The content is organized from the supplied Cloud Computing Lab Manual. Where the manual gives a procedure rather than an algorithm or source program, that original procedure is preserved instead of inventing unrelated content.
