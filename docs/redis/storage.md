# Redis Storage

All Redis servers per default uses ephemeral storage, meaning if the server reboots or are shutdown, the entire Redis server will be cleared for all data.

This is usually fine for using Redis for cache, since the data don't need to be consistent.

However this can't be used as an actual database with permanent data. For this we will later be adding a Block storage system to Redis, so redis servers can have persistent storage and backups.

This also means if you shutdown the redis server, the ephemeral disc will be purged.
