# Redis Storage

All Redis servers per default uses ephemeral storage, meaning if the server reboots or are shutdown, the entire Redis server will be cleared for all data.

This is usually fine for using Redis for cache, since the data doesn't need to be consistent.

However this can't be used as an actual database with permanent data.

This also means if you shutdown the redis server, the ephemeral disc will be purged.
