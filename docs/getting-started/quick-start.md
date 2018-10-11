# Quick start

## Setting up account

To get started on Vapor Cloud 2, setup a new account [here](https://dashboard.v2.vapor.cloud/signup)

![Signup](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-account.png)

After you have created your account, and signed in, you will see something like this

![Dashboard](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/dashboard.png)

!!! note
    During the Alpha, you will see various parts of the dashboard as "Under construction"

## Setup Git keys

Git keys gives you access to the Vapor Cloud Git. To setup git keys, you need to get the contents of the public SSH file.
Per default it's located at ~/.ssh/id_rsa.pub

To get the content you can do:

```bash
cat ~/.ssh/id_rsa.pub
```

It's only one line. Copy the file.

Under `Settings` in the menu, click the Create icon to create it.

![Setup key](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-key.png)

!!! note
    This might take a few seconds to create.

After this you should be able to verify access by running

```bash
ssh git@git.code.vapor.cloud
```

The output will look something like this:

```
PTY allocation request failed on channel 0
Hi jonas@vapor.codes, You've successfully authenticated to Vapor Cloud Git
 R W	night-long-14474
 R W	sun-ancient-43997
Connection to git.code.vapor.cloud closed.
```

## Setup your Vapor app, and Dockerfile

If you already have your Vapor app, simply use that, or run

```bash
vapor new my-application
```

Go into the app folder and let's setup the default Vapor 3 Dockerfile:

```bash
curl -O https://raw.githubusercontent.com/vapor-cloud/docker/master/Swift/Vapor3/web.Dockerfile
```
(This file can be modified to your needs if you want, but this will be working fine for most usecases.)

## Create your application

Click the `Applications` button, and click the `+` icon to create your application.

![Create application](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-application.png)

For `Name` if you select generated, it will create a random name for the application, this is great for testing. We will later add a feature allowing to change the app slug.

You can now see your application:

![See application](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/application-view.png)

From the `Git` card, copy/paste the git string, and go to your project and run

```bash
git remote add cloud [GitString]
git push cloud master
```

## Deploy

After you have pushed your code to the Cloud git server, you can start the deployment, by clicking the `Deploy` button in the Git card.

In the popup, it will use `Default branch`. If you want to deploy another branch, you can select `Custom branch` which will allow you to use another branch.

When you start the deployment, you automatically get all output from the deploy, making debug easy.

The last part of the deploy is `Launching` this will wait until the application is online. If the boot of the app fails, you will get the log output so you can see what failed.

![Deploy](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/deploy.png)

## Scale

After the deployment, your app isn't booted, since it will have 0 replicas. On the application page, it will also show as offline.

In the replicas card, click scale, and scale the app to e.g. 1 replica.

![Scale](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/scale.png)

After this you should be able to access your application on <app-slug>.v2.vapor.cloud

!!! note
    During Alpha apps will be available on **v2.vapor.cloud** we will be switching to **vapor.cloud** during Alpha

!!! note
    As we do have limited resources during Alpha, we advice you to keep your replicas small, if possible try to keep them at the free plan.

    Free plans in Cloud 2 provides 64mb memory, which should be enough for most use cases.
