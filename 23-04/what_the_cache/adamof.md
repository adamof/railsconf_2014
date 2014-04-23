What the cache?!
---
Simon Kröger

rails :race_condition_ttl
- good only if you use TTL to invalidate the cache

Solutions:
- ttl + race_conditions_ttl
- the application that changes the data, writes it to the cache as well
- content versioning <-- what they use

Marshalling is killing the CPU
Memcache is hit twice for each read

For storing the versioning they started using local hash + LRU algorithm














