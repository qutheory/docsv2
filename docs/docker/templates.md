# Docker Templates

We provide a variety of different Docker templates that can be found [here](https://github.com/vapor-cloud/docker)

## Vapor 3

The Vapor template takes advantage of a multi-stage build. This means it will first setup a container with the Swift compiler that will be used to build the application. After this, it will setup a plain Ubuntu container for running the compiled executable. 

This multi-stage build process results in a much smaller container, which allows for faster deployment, and faster boot up times. You can see the template [here](https://github.com/vapor-cloud/docker/blob/master/Swift/Vapor3/web.Dockerfile).

To set it up in your project, simply do:

```bash
curl -O https://raw.githubusercontent.com/vapor-cloud/docker/master/Swift/Vapor3/web.Dockerfile
```

!!! note
    There are a couple of lines you need to uncomment if you use Leaf/Public folder, instructions are in the file.
