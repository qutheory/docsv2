# Database Basics

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

!!! warning
    Please note, there are currently no backups of databases. If you don't want to risk losing your data,
    we recommend taking manual backups in intervals

## Setup a database

To setup a database, go to the application page, and click the `+` create icon in the top right corner. And click `Database`

After that select `Plan`, `Engine` and `Region`

![Create database](https://cloud2-cdn.ams3.cdn.digitaloceanspaces.com/create-database.png)

After creating the database, it's up and ready for being used.

!!! warning
    Your web replicas will reboot since it will add a config variable to the app. No deployment is necessary to update the config.

On the database card, you can see the `TOKEN` you can use in the database. You can also click the `More` button, and connection details, to see details giving you access to connect to the database from a Tool of your choice (CLI, GUI tool etc.)

Tokens are the one you connect to the database from your Vapor app. These are named like:

`DB_<ENGINE>` e.g. `DB_POSTGRESQL` if you have two databases of the same engine they will be named `DB_POSTGRESQL` and `DB_POSTGRESQL2`

## Connect in Vapor 3

### PostgreSQL

The following config will locally connect to localhost, and on Vapor Cloud use `DB_POSTGRESQL` variable.

```swift
services.register { c -> PostgreSQLDatabaseConfig
    switch c.environment {
    case .development:
        return .init(
            hostname: "localhost",
            port: 5432,
            username: "vapor",
            password: "vapor",
            database: "database"
        )
    default:
        guard let url = Environment.get("DB_POSTGRESQL") else {
            throw Abort(.internalServerError, reason: "No DB_POSTGRESQL env var set")
        }
        guard let config = try PostgreSQLDatabaseConfig(url: url) else {
            throw Abort(.internalServerError, reason: "Could not create PostgreSQL config from DB_POSTGRESQL env var")
        }
        return config
    }
}
```

### MySQL

The following config will locally connect to localhost, and on Vapor Cloud use `DB_MYSQL` variable.

```swift
services.register { c -> MySQLDatabaseConfig
    switch c.environment {
    case .development:
        return .init(
            hostname: "localhost",
            port: 3306,
            username: "vapor",
            password: "vapor",
            database: "database"
        )
    default:
        guard let url = Environment.get("DB_MYSQL") else {
            throw Abort(.internalServerError, reason: "No DB_MYSQL env var set")
        }
        guard let config = try MySQLDatabaseConfig(url: url) else {
            throw Abort(.internalServerError, reason: "Could not create MySQL config from DB_MYSQL env var")
        }
        return config
    }
}
```
