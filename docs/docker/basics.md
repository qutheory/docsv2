# Docker Basics

All applications on Vapor Cloud runs in a Docker container. This gives full flexibility over
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

## Testing locally

This allows you to build and test the Docker container locally. To do this you can build it with e.g.:

```bash
docker build -t my-app -f web.Dockerfile
```

And then you can run it

```bash
docker run -ti -p 8081:80 my-app
```
And test it with http://127.0.0.1:8081

!!! note
    Because of the complex nature of the Vapor Cloud setup, you might experience differences between
    local and live results.

## Port settings

Applications inside the container need to listen on port **80**

For Vapor you should start the process with `--port 80` to achieve this.

If it listens on another port, the application won't work.

!!! note
    The Docker EXPOSE feature is not supported, and will be ignored.
