# Factors to Consider while creating cache
## Talk about Eviction Policy
  - LRU (least recently used)
  - FIFO (first in first out)
## Talk about TTL (time to live)
  - low TTL
    - when we need high accuracy 
  - High TTL
    - when we dont need high accuracy
    - when high cache hit is more desirable 
    - when downstream is not changing more frequently
    

## Thundering Herd Problem
  - due to serveral cache expiring at same time
  - can be solved by adding jitter on cache expiration
    (Jitter in cache expiration is a technique that involves adding random variations to the time-to-live (TTL) value of cache entries. This causes cache entries to expire at slightly different times, rather than all at once.)
