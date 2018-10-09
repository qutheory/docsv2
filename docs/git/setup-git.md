# Setup git

All applications on Vapor Cloud get a **free** private repository on Vapor Cloud.
You can easily use this to deploy your Application from.

Before you can use it, you need to setup your public key on Vapor Cloud.

## Setup Public key

!!! note
    TODO

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
