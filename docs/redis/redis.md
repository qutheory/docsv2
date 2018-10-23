# Redis

!!! note
    More info when the product is available

Redis allows for creating Redis servers, which is a good way to do e.g. Cache in your app.

This means if you need to fetch large amounts of the same data from your app, you can cache the data in Redis.

When creating a Redis product, you get your own server, only used for that specific environment, meaning no shared data with other clients. Even on the free plan.

## External access

It's possible to connect to Redis servers externally, either through CLI or GUI interface for easy debugging Redis.

Each redis server have a password, that can be easily rotated for security.

!!! note
    Later it will also be possible to setup IP Whitelist, to only allow certain ips to access the redis server.
