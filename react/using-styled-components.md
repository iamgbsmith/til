# Using Styled Components

styled-components utilise tagged template literals to style your components and remove the mapping between components and styles. This allows for creating a normal React component that has styles attached to it.

### Install styled-components packages

```shell
yarn add styled-components @types/styled-components
```

### Create a styled component

The following example creates `styled.div` and `styled.span` components for a React functional component with styles attached.

```javascript
import React from 'react';
import styled from 'styled-components/macro';

interface HeaderProps {
  readonly title: string;
  readonly description: string;
}

const HeaderWrapper = styled.div`
  flex: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 1em;
  padding: 1em;
  border-radius: 3px;
  background-color: green;
`;

const Title = styled.span`
  font-size: 2.5em;
  font-weight: bold;
  color: white;
`;

const Description = styled.span`
  font-size: 1.5em;
  color: white;
`;

function Header({ title, description }: HeaderProps) {
  return (
    <HeaderWrapper>
      <Title>{title}</Title>
      <Description>{description}</Description>
    </HeaderWrapper>
  );
}

export default Header;
```

See [styled-components](https://styled-components.com) for more details.