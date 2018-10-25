# Replica Storage

!!! warning
    All replicas use ephemeral storage

## Ephemeral storage

Ephemeral storage is a temporary disc storage created for all Replicas in Vapor Cloud.
This gives a way to store the application on Vapor Cloud.

It's important to know that everytime a replica is shutdown/rebooted the ephemeral storage
will be deleted, and a new drive is created. This means if you e.g. Store an image during runtime
and the application reboots (Crashes, redeploy etc.) Everything not in Git will be deleted.

## Block storage

!!! note
    We are planning on building Block storage, allowing for stable storage, however it's not ready yet.
