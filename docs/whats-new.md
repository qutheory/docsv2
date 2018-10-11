# What's New in 2.0

Vapor Cloud 2 is a complete rewrite of all parts of the system. This has allowed us to make the service a lot more flexible while adding new features in the process.

On this page we will outline some of the biggest differences you will experience when using Vapor Cloud 2.

## Organization and Permissions

Permissions have been simplified. When inviting a person to your organization, that person will have access to all applications under that organization.

We are working with the following roles:

| Role name | Description |
| --------- | ----------- |
| admin | This is the admin account. This person has full access to create, update, and delete organizations and applications. |
| developer | This account can create and update organizations and applications, but can't delete. They also can't access billing details. |
| billing | This account can only access billing details. |

!!! notice
    We generally advice to have a few admins, since these can delete applications and all related data.

## Projects, Hosting, and Applications

The concepts of Projects and hosting have been **deprecated** to make the system simpler.

Applications and environments work a lot like Cloud 1 with minor differences.

## Multiple Replicas

We have prepared (but not built yet) support for having multiple replica types, so it will be possible to have the same codebase but with different Docker templates. This will allow you to, for example, have a `queue` container to handle larger async tasks in a different replica with different resources.

All applications automatically have a replica called `web` which is the primary replica accepting normal web requests.

A lot more about this system later.

## Git

Vapor Cloud 2 gives all applications a free Git private git repository that can be used to deploy. It is still possible to use GitHub, Gitlab, or Bitbucket for collaboration, but deployments must be done through our Git server

This will allow people to only upload one or more public SSH keys, this key is public, and is the same you e.g. Do when you upload your key to e.g. GitHub.When you invite a person to your organization they are automatically given access to your applications on our Git server.

You can read more about Git [here](/git/basics.md)

## cloud.yml and Dockerfile

The **cloud.yml** file from Cloud 1 have been **deprecated** and instead the project should contain a Dockerfile.

This provides a lot more flexibility e.g. To be able to customize the containers running the project
and to even support other types of sites like Kitura, Perfect, and even PHP etc.

The file should be named e.g. `<replicaSlug>.Dockerfile` For example `web.Dockerfile`

Read more about Docker [here](/docker/basics.md)

!!! note
    You app need to accept requests on port **80** For vapor you can do `--port 80`
    The `EXPOSE` feature from docker is **NOT** supported and will be ignored.
