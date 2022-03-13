# Reset Recoil State

__Category: React__

Recoil state can be reset using a call to `useResetRecoilState`.

Assume an atom called `ordersAtom`:

```javascript
import { atom } from 'recoil';

export const ordersAtom = atom<string[] | undefined>({
  key: 'ordersState',
  default: [],
});
```

Reset the value of the state to its default value as follows:

```javascript
import { useResetRecoilState } from 'recoil';
// ...
import { ordersAtom } from '../atoms/ordersAtom';
// ...
const resetOrders = useResetRecoilState(ordersAtom);
// Reset orders to the default state
resetOrders();
````

See [useResetRecoilState(state)](https://recoiljs.org/docs/api-reference/core/useResetRecoilState) for more details.
