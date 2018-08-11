# Hash Tables

* Uses a dictionary/map data type
  * Key maps to bucket/value
* Hash collisions occur when keys aren't unique
  * Keys are converted to hash codes which are converted to array indices
  * Infinite number of keys vs finite number of hash codes is what can cause collision
* Pros: speed, especially when entries are predictable -- mostly O(1)
* Cons: Not as effective when # of entries is very small, cannot be enumerated efficiently (pseudo-random)
* Amortized constant-time: Hash table functions are--on average--completed in O(1), however, due to collisions or table resizing, a single operation might take *much* longer

* An example hash function might be adding up character codes of each character in string. You then divide by modulus of total inputs so you get a number, `0` to `length(input) - 1`, which would be the indices of the array

## Collision Mitigation

As # of keys grows, likelihood of hashing into the same bucket increases. Most hash table implementations have a collision resolution strategy. All of them require that the keys be stored along with their values.

### Separate Chaining

![Separate Chaining](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Hash_table_5_0_1_1_1_1_1_LL.svg/675px-Hash_table_5_0_1_1_1_1_1_LL.svg.png)

* Each bucket is independent and will have multiple, chained entries to resolve collisions

### Open Addressing

![Open Addressing](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Hash_table_5_0_1_1_1_1_0_SP.svg/570px-Hash_table_5_0_1_1_1_1_0_SP.svg.png)

* All entry records are stored in the bucket, itself
* When a collision occurs, an open bucket is search for (generally consecutively) and the entry is placed there, instead
* When searched, buckets are scanned at expected bucket first, then until an empty bucket is found. If an empty bucket is found, there is no such key in the table
* Better for tables with low load factor, smaller records/elements, and similarly-sized data