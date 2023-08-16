# Create An Index In RediSearch

__Category: Redis__

RediSearch is an enterprise search extension for Redis and ships with the Redis Server stack. It provides support for querying, secondary indexing, and full-text search including wildcard and fuzzy search.

Assuming a dictionary structure of the following:

```json
mapping={
    "manufacturer": manufacturer,
    "model": model,
    "weight": weight,
    "description": description,
}
```

Create an index for searching against the `description` field:

```shell
FT.CREATE inventory-description-idx PREFIX 1 inventory: SCHEMA description TEXT
```

To search for the word "touring" using wildcards against the description field:

```shell
FT.SEARCH inventory-description-idx "%touring%"
```
