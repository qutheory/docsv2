# Dashboard Basics

The dashboard in Vapor Cloud 2 is an easy way to interact with your workloads on Vapor Cloud. This page will give you the highlights of how to use it.

## Navigation

### Search

At the top of the Dashboard, there is a Search field. This searches for Applications across all organizations you have access to. Once you start typing, it will automatically start showing you results.

![Search](https://cloud2-cdn.ams3.digitaloceanspaces.com/search.png)

### Organization Switcher

At the top of the main menu, you can see the currently selected organization. If you click the button next to the name, you get a can switch to a different organization.

![Organization switcher](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/org-switcher.png)

## Application

### Actions

At the top of the application view page, there is an action bar with two main functions:

- Environment Switcher: Select which of the application's environments you are viewing.
- `+` Button: Used to create Environments, Databases, etc.

![Application actions](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/application-actions.png)

### Cards

Under the application view page, there are several, dynamic cards. These show various features of the application and are your primary method of interaction.

![Application card](https://user-images.githubusercontent.com/2535140/46768337-1ca73800-cce8-11e8-9af5-1474bfbab5b3.png)

On each card, there can be zero or more main action buttons. These help you perform common tasks quickly, like deploying or scaling your application. 

On some cards, there can be a "more" button in the top right corner. Clicking the more button gives access to less common tasks, like viewing database credentials.

### Status

The application status card, is connected directly to the cluster, this means you get a live status of replicas running.

This means after scaling or deployment, the number can be a bit different depending on when all
changes are updated in the cluster.

![Application status](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/card-status.png)
