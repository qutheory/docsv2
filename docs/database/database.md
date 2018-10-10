# Database

Vapor Cloud supports two different database engines `MySQL` and `PostgreSQL`.

Depending on the plan, there are two different ways the databases are issued:

| Plan | Provision |
| ---- | --------- |
| Dev - Free | A database on a shared server |
| Dev - Hobby | A database on a shared server |
| Standard-* | Own database server |

Dev plans are row limited, and there are no customization of the system. There are also minimal flexibility in versions.

For Standard-* plans, you get your own server, and are able to setup IP Whitelisting to only allow specific ips access for security.
You are also able to customize parts of the configuration to fit your need.

## Setup a database

To setup a database, go to the application page, and click the `+` create icon in the top right corner. And click `Database`

After that select `Plan`, `Engine` and `Region`

![Create database](https://user-images.githubusercontent.com/2535140/46724819-1dee4b80-cc7b-11e8-95fb-66da1e44e163.png)

After creating the database, it's up and ready for being used.

!!! note
    Your web replicas will reboot since it will add a config variable to the app. No deployment is necessary to update the config.

On the database card, you can see the `TOKEN` you can use in the database. You also have an `Open` button, if you click this, you get credentials for external connection to the database.

Tokens are the one you connect to the database from your Vapor app. These are named like:

`DB_<ENGINE>` e.g. `DB_POSTGRESQL` if you have two databases of the same engine they will be named `DB_POSTGRESQL` and `DB_POSTGRESQL2`

To connect to it from your Vapor 3 app, simply use:

```swift
let databaseConfig: PostgreSQLDatabaseConfig
let url = Environment.get("DB_POSTGRESQL")

guard let urlConfig = PostgreSQLDatabaseConfig(url: url) else {
    fatalError("Failed to create PostgreSQLConfig")
}
databaseConfig = urlConfig
```
