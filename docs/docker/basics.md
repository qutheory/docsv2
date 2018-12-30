# Docker Basics

All applications on Vapor Cloud run in a Docker container. This gives full flexibility over
what is installed for the specific applications.

Docker files in Vapor Cloud 2 should be located in the root directory (Same place as your `Package.swift` file)

## Naming

The Dockerfile need to be named after a specific naming scheme.

The name should be `<replicaName>.Dockerfile`

For example:

| Replica name | Dockerfile name |
| ------------ | --------------- |
| web (default) | web.Dockerfile |
| queue | queue.Dockerfile |

## Testing Locally

You can use Docker or Docker Compose to test your application locally.

!!! note
    You may experience differences between local and deployed results.

### Manual Docker

You can build and run your Docker containers manually using `docker build` and `docker run`.

```bash
docker build -t my-app -f web.Dockerfile
```

Then run your application with the following command:

```bash
docker run --rm -it -p 8080:80 my-app
```
And test it by visiting `http://127.0.0.1:8080`.

!!! note
    If you use the default dockerfile provided in the Vapor templates, make sure to add `--build-arg env=docker` to your build command, and add any required environment checks using `Environment.custom(name: "docker")`

### Docker Compose

You can also use Docker Compose to manage your local test images and containers by creating a `docker-compose.yml` in the root of your project.

```yml
version: '3'
services:
  web:
    ports:
     - 8080:80
    build:
      context: .
      dockerfile: web.Dockerfile
```

Once saved, you can use the following command to boot your project for testing.

```
docker-compose up --build web
```

The `--build` flag will ensure the image is rebuilt with each run.

### Port Settings

Applications inside the container need to listen on port **80**. If it listens on another port, the application won't work.

!!! note
    The Docker EXPOSE feature is not supported, and will be ignored.
