# Quick start

## Setting up account

To get started on Vapor Cloud 2, setup a new account [here](https://dashboard.v2.vapor.cloud/signup)

After you have created your account, and signed in, you will see something like this

![Dashboard](https://user-images.githubusercontent.com/2535140/46662530-f97f6a00-cbbb-11e8-85cc-11fa5e53406b.png)

!!! note
    During the Alpha, you will see various parts of the dashboard as "Under construction"

## Setup Git keys

!!! note
    @TODO!!

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

![Create application](https://user-images.githubusercontent.com/2535140/46663583-c7bbd280-cbbe-11e8-805a-94aa03b940eb.png)

For `Name` if you select generated, it will create a random name for the application, this is great for testing. We will later add a feature allowing to change the app slug.

You can now see your application:

![See application](https://user-images.githubusercontent.com/2535140/46664278-d30ffd80-cbc0-11e8-8b08-fb9ac80b3696.png)

From the `Git` card, copy/paste the git string, and go to your project and run

```bash
git remote add cloud [GitString]
git push cloud master
```

## Deploy
