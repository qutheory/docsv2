# Setup Config

Configurations are an easy way to store sensitive information in your app. For example API keys etc.

Configs in Vapor Cloud are provided to the specific container through Environment variables.

Configs are unique to each environment, and shared between all replicas in the specific environment.

## Create configs

To setup Config, click the 3 dots on the Application card, and click `Configuration`

Input your new config variables

![Update config](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-config.png)

And click `Update`

!!! warning
    This will cause a reboot of the application to update the config vars. No deployment is necessary to update the config.

## Use configs in Vapor

You can use the environment variables in Vapor 3 like the following

```swift
var myKey = Environment.get("MY_KEY")
print(myKey) // MY_VALUE
```
