# Dashboard Basics

The dashboard in Vapor Cloud 2 is an easy way to interact with your workloads on Vapor Cloud.

This page will give you the highlights of how to easily use it.

## Search

At the top of the Dashboard, there are a Search field. This will give you access to search for Applications across all organizations you have access to. Once you start typing, it will automatically start showing you results.

![Search](https://cloud2-cdn.ams3.digitaloceanspaces.com/search.png)

## Organization switcher

In the top of the menu, you can see the currently selected organization. If you click the button next to the name, you get a popup to switch to a different organization.

![Organization switcher](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/org-switcher.png)

## Application actions

At the top of the application view page, there are an action bar. This have to main functions.

First is the environment switcher, here you can select which environment you want to use.

Next there are a create button, which can be used to create Environments, Databases etc.

![Application actions](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/application-actions.png)

## Application cards

Under the application view page, there are a lot of cards, these show various features for the application.

For example a card for each Replica, each database etc.

On the card there are two types of buttons, in the top right corner there can be a `More` button (3 dots), this opens a popup with various features.
Aside from that, there can be one or more actions buttons in the bottom of the card.

![Application card](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/card.png)

### Application status

The application status card, is connected directly to the cluster, this means you get a live status of replicas running.

This means after scaling or deployment, the number can be a bit different depending on when all
changes are updated in the cluster.

![Application status](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/card-status.png)
