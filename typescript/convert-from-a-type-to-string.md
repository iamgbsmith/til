# Convert From A Type To String

__Category: TypeScript__

Assume the following type definition:

```javascript
export type MatchType = string | null | undefined;

export interface SelectedLetter {
  letter: string;
  matchType: MatchType;
}
```

With an array:

```javascript
const keys: SelectedLetter[] =
  [
    { letter: 'a', matchType: 'none' },
    { letter: 'b', matchType: 'none' }
  ];
```

Attempts to access the `matchType` value from an array element as a string:

```javascript
let foo: string = keys[index].matchType;
```

...will raise a compiler error stating: `Type 'MatchType' is not assignable to type 'string'`.

The solution is to convert the value to a string, use the following call:

```javascript
let foo: string = String(keys[index].matchType);
```
