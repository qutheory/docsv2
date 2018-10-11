# Config Basics

Config vars are an easy way to store sensitive information in your app. For example API keys etc.

Configs in Vapor Cloud are provided to the specific container through the ENV (process environment). Configs are unique to each environment and shared between all replicas.

## Create Configs

To setup Config, click the more button on the Application card, and click `Configuration`.

Input your new config variables.

![Update config](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-config.png)

Then, click `Update`

!!! warning
    This will cause a reboot of the application to update the config vars. No deployment is necessary to update the config.
