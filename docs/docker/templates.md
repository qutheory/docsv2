# Docker Templates

We provide a variety of different Docker templates, that we feels give the best
system.

All templates can be found [here](https://github.com/vapor-cloud/docker)

## Vapor 3

The Vapor template is built using Multi-stage build. This means it will first setup
a full Swift container, this will be used to build the application.

After this it will setup a plain Ubuntu container where it will copy important files.

This gives a much smaller container, which allows for faster deployment, and faster boot up times.

You can see the template [here](https://github.com/vapor-cloud/docker/blob/master/Swift/Vapor3/web.Dockerfile)

To set it up in your project, simply do:

```bash
curl -O https://raw.githubusercontent.com/vapor-cloud/docker/master/Swift/Vapor3/web.Dockerfile
```

!!! note
    There are a couple of lines you need to uncomment if you use Leaf/Public folder, instructions are in the file.
