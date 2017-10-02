# Auth Microservice

This repository contains the authentication (auth) microservice from Udacity's server-side Swift curriculum. The auth microservice is a simple Swift server that exposes two endpoints:

- /
  - returns an "ignore" notice
- /login
  - when provided a valid username/password, returns an auth token

To experiment with the endpoints, see the [Lesson 1: Authentication Microservice Docs on Apiary](http://docs.l1auth.apiary.io/#).

Also, the auth microservice uses the Swift Package Manager to manage dependencies.

## Swift Dependencies

- Kitura
- HeliumLogger
- Kitura-Credentials
- Kitura-CredentialsHTTP
- Perfect-Crypto

## How to Use

The auth microservice can technically be built to run on macOS or Ubuntu Linux. However, we recommend building for Ubuntu Linux since that will likely be the environment used if you were to deploy the microservice into the cloud. Furthermore, to assure consistency between development and possible deployment environments, Docker is used. Take the following steps to build and run the monolith:

**1] Build the Docker Image**

```bash
docker build -t s3-auth:1.0.0 .
```

**2] Run the Docker Image (start Bash shell)**

```bash
docker run --rm -it -v $(pwd):/app -p 8082:8082 s3-auth:1.0.0 /bin/bash
```

**3] Build the Microservice**

```bash
# assuming you are located at /app
swift build
```

**4] Run the Microservice**

```bash
# assuming you are located at /app
.build/debug/auth
```

**5] Test an Endpoint!**

```bash
curl localhost:8082/login -uusername
Enter host password for user 'username': password
```
