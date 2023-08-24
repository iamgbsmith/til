# Count Items Matching A Search Criteria

__Category: Redis__

### Count the number of items in a search index

Count the number of items in a Redis search index called "player-name-idx" using LIMIT 0 0

```shell
FT.SEARCH player-name-idx "*" LIMIT 0 0
```

### Count the number of items matching a search criteria for a field

Count all matches in a Redis search index called "player-name-idx" where the value for the `name`` field contains
`smith`:

```shell
FT.SEARCH player-name-idx "@name: smith" LIMIT 0 0
```

__Note:__

Searches in Redis are case insensitive. For example, "Smith" equates to "smith".
