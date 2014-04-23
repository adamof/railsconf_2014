What the cache
==================
Simon Kroger

ActiveSupport::Cache::Store

:race_condition_ttl
- it avoids a race condition of all processes detecting a cache invalidation
and all try at same time writing to the cache key
- should be kept small

Strategies
- race_condition_ttl
- the applicationg changing the content writes it to
the cache
- content versioning

DB has still a limit of how many queries per second can be done

cache number on memcache

Marshalling
- objects to strings takes a lot of CPU
- YAML slowest
- MessagePack and Oj, the fastest

Our solution
- Hash + LRU algorithm

