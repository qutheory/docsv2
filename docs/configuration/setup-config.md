# Setup Config

To setup Config, click the 3 dots on the Application card, and click `Configuration`

Input your new config variables

![Update config](https://user-images.githubusercontent.com/2535140/46725376-593d4a00-cc7c-11e8-8ef3-621f2afb9aad.png)

And click `Update`

!!! warning
    This will cause a reboot of the application to update the config vars. No deployment is necessary to update the config.

You can use the environment variables in Vapor 3 like the following

```swift
var myVar = Environment.get("MY_VAR")
print(myVar) // MY_VAL
```
