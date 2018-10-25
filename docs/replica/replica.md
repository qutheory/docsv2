# Replica

Replica are our product for hosting applications. Each replica is a full container based on the specs in the Dockerfile specified in the project.

When a replica is deployed or changed, our system will assign each replica to an available worker node. If an environment have multiple replicas, our system will try to assign each replica to different worker nodes, so if one crashes, the app is still available.

Depending on the plan selected we have two different sizes of worker nodes.

| Plans | Worker node | Description |
| ---- | ----------- | ----------- |
| Dev Free / Dev Hobby | web-free | Worker node with minimal CPU for developing purpose |
| Other plans | web | Worker node with larger CPU, allowing for small CPU bursts above the plans limitations |

## CPU Limitations

*CPU is a soft limit*

Each replica plan will have a certain amount of CPU allowed to be used. If a Replica goes above it's CPU limit,
the admin of the organization will receive an Email.

If the CPU limit keeps being above the limit, the replica will be rebooted.

If it still keeps above the limit the replica will be shutdown.

## Memory Limitations

*Memory is a hard limit*

Each replica plan will have a certain amount of Memory allowed to be used. If a replica reaches it's memory limit, the replica will reboot, this reboot usually takes 4-5 seconds.

All crashes will be shown from the logs.
