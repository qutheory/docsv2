When developing your app, you sometimes need to use a dependency from a private git repository.

To do this, you need to upload a private git key as an environment variable, and make some changes to your Dockerfile.

1. First make a Base64 encoded string of your private key.

```
cat /path/to/file | base64
```

Setup the value of this under the Environment variable key `SSH_PRIVATE_KEY` in Vapor Cloud 2

2. Add the following lines to your `web.Dockerfile`

```
ARG ssh_prv_key=""

# Authorize SSH Host
RUN mkdir -p /root/.ssh && \
    chmod 0700 /root/.ssh && \
    ssh-keyscan github.com > /root/.ssh/known_hosts && \

# Add the keys and set permissions

RUN echo "$ssh_prv_key" | base64 -d > /root/.ssh/id_rsa && \
    chmod 600 /root/.ssh/id_rsa
```

This will add the specified key to the container in order to download the private dependencies.