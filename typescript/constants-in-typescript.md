# Constants In TypeScript

__Category: TypeScript__

Constants in TypeScript should be contained in classes which have the sole purpose of defining constant values.

Create a `constants.ts` file which declares your constants:

```javascript
export abstract class Constants {
  static readonly MAX_VALUE: number = 14703;
  //...
}
```

Important the constants file and use the constant value:

```javascript
import { Constants } from './constants';

//...

// Obtain a random number between 0 and the max value defined by the constant
const randomNumber = Math.floor(Math.random() * Constants.MAX_VALUE);
```
