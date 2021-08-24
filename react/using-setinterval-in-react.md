# Using SetInterval In React

__Category: React__

You can use the `setInterval` timer in a React component with React Hooks. The following example will update the value for `count` every 1000 milliseconds.

```javascript
import React, {useEffect, useState} from 'react';
import styled from 'styled-components/macro';

const CounterText = styled.span`
  font-size: 1.5em;
  font-weight: bold;
  color: white;
`;

function Counter(initialCount: number) {

  const [count, setCount] = useState(initialCount);

  useEffect(() => {
    const interval = setInterval(() => {
      setCount(count => count + 1);
    }, 1000);
    return () => clearInterval(interval);
  }, []);

  return (
    <div>
      <CounterText>{count}</CounterText>
    </div>
  );
}

export default Counter;
```

The timer will be cleared when the component is destroyed.
