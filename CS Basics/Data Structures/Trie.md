# Trie (Pronounced Tree)

![Trie](https://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Trie_example.svg/375px-Trie_example.svg.png)

* A type of search tree but keys aren't stored in nodes
  * Instead, its position defines the key
    * In the above picture, the edges are parts of the key and then the node's key is the combined path. Down the left, "to" comes from the "t" node and then the "o" edge
    * Keys are generally the leaves
* Generally keyed by character strings
* Used frequently with predictive text and autocomplete

## Advantages

* Faster than imperfect hash table in the worst case -- O(m) where m is the length of the search string
* No collisions
* Can provide alphabetical ordering

## Disadvantages

* Lookup can be slower than some hash tables
* Sometimes requires more space than a hash table since memory may be allocated to each character, rather than a single chunk for the whole string
