# Quick Start

This guide will walk you through all of the required steps for deploying your first app in Vapor Cloud 2.

## Signup

To get started on Vapor Cloud 2, setup a new account [here](https://dashboard.v2.vapor.cloud/signup).

![Signup](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-account.png)

After you have created your account, and signed in, you will see something like this:

![Dashboard](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/dashboard.png)

!!! note
    During the Alpha, you will see various parts of the dashboard as "Under construction".

## Setup Git Access

Git keys give you access to Vapor Cloud's private Git server. To setup git keys, you need to get the contents of your public SSH file. It's usually located at `~/.ssh/id_rsa.pub`, but my vary.

To get the content you can run the following command:

```bash
cat ~/.ssh/id_rsa.pub
```

Alternately you can get the content of the key directly on your clipboard:

```bash
pbcopy < ~/.ssh/id_rsa.pub
```

It's only one line. Copy the entire output.

Next, in the dashboard, navigate to the Settings page using the main menu. Then, click the `+` button in the SSH keys section.

![Setup key](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-key.png)

Give your SSH key a recognizable name and paste the contents of the key. Then, click create.

!!! note
    This might take a few seconds to create.

After this you should be able to verify access by running.

```bash
ssh git@git.code.vapor.cloud
```

The output will look something like this:

```
PTY allocation request failed on channel 0
Hi jonas@vapor.codes, You've successfully authenticated to Vapor Cloud Git
 R W    night-long-14474
 R W    sun-ancient-43997
Connection to git.code.vapor.cloud closed.
```

## Prepare your Project

In order to run on Vapor Cloud, a project needs to define a `web.Dockerfile`. This is responsible for building the project and finally booting a server to handle HTTP requests on port 80.

We offer a growing collection of `Dockerfile` templates for various web frameworks at [vapor-cloud/docker](https://github.com/vapor-cloud/docker). If the framework you are deploying is there, just copy the `web.Dockerfile` into your project and commit it.

You can always create your own `web.Dockerfile` if you want. Visit [Docker &rarr; Basics](/docker/basics.md) for more information.

## New Application

Next, we need to create a new application in Vapor Cloud to host our project. Go to the Applications page using the main menu, then click the `+` icon to create a new application.

![Create application](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-application.png)

For `Name`, let's let Vapor Cloud generate a unique name for our application by selecting `Generated`. Choose a plan and region to host your application in, then click create.

You can now see your application:

![See application](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/application-view.png)

Click the "More" icon on the Git card, and view the instructions for configuring Git.

## Deploy

After you have pushed your code to Vapor Cloud's private git server, you can start the deployment. Click the `Deploy` button on the Git card. By default the deployment will use the environment's `Default Branch` (`master`). If you want to deploy another branch, you can select `Custom Branch`, or create a new environment.

When you start the deployment, you automatically get all output from the deploy, making debugging easy. The last part of the deploy is `Launching`. This will wait until the application is online. If booting the app fails, you will get the log output so you can see what failed.

![Deploy](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/deploy.png)

## Scale

After deploying your app for the first time, you must scale the application to one or more replicas to bring it online. Subsequent deployments will not require you to re-scale your application.

On the Replica card, click scale, and scale your app to `1`.

![Scale](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/scale.png)

After this you should be able to access your application on `<app-slug>.v2.vapor.cloud`

!!! note
    During Alpha apps will be available on **v2.vapor.cloud** we will be switching to **vapor.cloud** during Alpha

!!! note
    As we do have limited resources during Alpha, we advice you to keep your replicas small, if possible try to keep them at the free plan.

    Free plans in Cloud 2 provides 64mb memory, which should be enough for most use cases.
