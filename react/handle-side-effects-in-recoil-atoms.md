# Handle Side Effects In Recoil Atoms

__Category: React__

Atom effects are an API in Recoil for handling side-effects in atoms. For example, you can use a side effect to log when a change is made to application state or you can use a side effect to update a value in local storage.

Assume you have a value for your application that you need to log a change for and persist to local storage, add a side effect to your atom in the `effects` block with an `onSet` method as follows:

```javascript
import { atom } from 'recoil';

export const darkModeAtom = atom({
  key: 'darkModeState',
  default: (localStorage.getItem('darkMode') === 'true'),
  effects: [
    ({onSet}) => {
      onSet(darkMode => {
        console.debug(`Dark mode is ${darkMode}`);
        localStorage.setItem('darkMode', Boolean(darkMode).toString());
      });
    },
  ],
});
```

See [Atom Effects](https://recoiljs.org/docs/guides/atom-effects/) for more details.
