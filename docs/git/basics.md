# Git Basics

All applications on Vapor Cloud get a **free** private repository on Vapor Cloud.
You can easily use this to deploy your Application from.

Before you can use it, you need to setup your public key on Vapor Cloud.

## Setup Public key

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

## Setup Git

If you already have a Vapor app, you can easily setup your repository locally.

To do this, run the following command

```bash
git remote add cloud git@git.code.vapor.cloud:...
```

!!! note
    We always recommend setting up the Vapor Cloud git on the `cloud` remote, so you can keep e.g. Github on `origin`

!!! note
    You need to replace `...` with your app slug, you can get the full remote from the dashboard.

### Push to git

To push to git, simply do

```bash
git push cloud master
```

## Test access

To verify you have access, you can run

```bash
ssh git@git.code.vapor.cloud
```

This will print output with your Vapor Cloud Email, and a list of applications you have access to.
