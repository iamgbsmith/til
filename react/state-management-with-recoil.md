# State Management With Recoil

__Category: React__

Recoil is a state management library for React applications based around the concept of `atoms` and `selectors`. It is a viable alternative to Redux and MobX due to it being more verbose and requiring less boilerplate code. 

This example will convert a decimal value to a binary value.

Add Recoil to your project:

```shell
yarn add recoil
```

To use Recoil state inside the components, wrap them within a root component called `RecoilRoot`. If all components need to access shared state, do this in the top-most component in the hierarchy.

```javascript
import React from 'react';
import BinaryConverter from './components/binaryconverter';

import {
  RecoilRoot,
} from 'recoil';

const App:React.FC = ()=> (
  <>
    <RecoilRoot>
      <BinaryConverter/>
    </RecoilRoot>
  </>
)

export default App;
```

### Atoms

Atoms are units of state with two fields: a (unique) key, and a default value. Atoms are mutable and can be accessed from any component. 

```javascript
import { atom } from 'recoil';

const numberAtom = atom({
  key: 'numberState', // unique ID to prevent clashes with other atoms/selectors
  default: '0', // default value (aka initial value)
});

export { numberAtom };
```

Components that read the value of an atom are implicitly subscribed to that atom and re-rendered when state changes.

```javascript
import {
  useRecoilState,
} from 'recoil';

//...

function BinaryConverter() {
  return (
    <div>
      <NumericInput />
      <BinaryValue />
    </div>
  );
}

function NumericInput() {
  const [number, setNumber] = useRecoilState(numberAtom);

  const onChange = (event) => {
    // Check that an integer value has been typed
    if (Number.isInteger(event.target.value)) {
      setNumber(event.target.value);
    }
  };

  return (
    <div>
      <input type="text" value={number} onChange={onChange} />
    </div>
  );
}
```

### Selectors

State can be used in other components using a `selector` which represents derived state.

```javascript
import {
  selector,
} from 'recoil';

const binarySelector = selector({
  key: 'binaryValueState', // unique ID to prevent clashes with other atoms/selectors
  get: ({get}) => {
    const number = get(numberState);
    return (number >>> 0).toString(2); // convert number to binary value
  },
});

export { binarySelector };
```

With the `useRecoilValue()` hook, you can read the value of binaryValueState in your component:

```javascript
import {
  useRecoilValue,
} from 'recoil';

//...

function BinaryValue() {
  const binaryValue = useRecoilValue(binaryValueState);
  return <>Binary value of number is: {binaryValue}</>;
}
```

There are no must-follow rules with regards to where atoms and selectors should be stored in your project tree however one approach is to store them in `/atoms` and `/selectors` under the `/src` directory. 

Larger projects may be better suited to following the "Ducks", or feature based-project structure pattern.

See [Recoil](https://recoiljs.org/) for more details.

