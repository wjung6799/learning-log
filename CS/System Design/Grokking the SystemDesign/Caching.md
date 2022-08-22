# Caching

## Application server cache

This is a technique where cache is stored in the application. So it could be in memeory or local disk data. However with distributed system, cache miss can occur as loadbalancer will randomly hit whatever server is availalbe.

## Content Delivery Network

Using CDN, we move static media files closer to the user who recently accessed it. Using lightweight http server like Nginx we can make a seperate subdomain

## Cache Invalidation

Cache invalidation occurs when a cache data is outdated since the data was modified in the database.

3 main schemes used are below:

1. **Write-through cache**: Writes to both database and cache when update occurs. It is less likely to fail but it is expensive.
2. **Write-around cache**: This method bypasses the cache writing and directly writes to the database. Obviously cache miss will occur as it does not update the cache and higher latency because it has to retrieve the data from the server
3. **Write-back cache**: This only updates the cache. Therefore client experiences immediate feedback but risky in terms of data loss.

## Cache eviction policies

1. FIFO(First in First Out)
2. LIFO(Last in First Out)
3. LRU(Least Recently Used)
4. MRU(Most Recently Used)
5. LFU(Least Frequently Used)
6. RR(Random Replacement)
