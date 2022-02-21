# Conditional CSS In Styled Components

__Category: React__

Styled components support dynamic styling with conditional CSS. This example will create a styled `h1` in TypeScript with an optional parameter that can be used to specify display of a border.

```javascript
import styled, { css } from 'styled-components';

export const Heading = styled.div<{border?: boolean}>`
  font-size: 32px; 
  margin: 20px;
  text-align: center;
  padding: 20px;
  ${props => props.border === true && css`
      border: 1px solid #0f0f0f;
  `}
`;
```

Use the styled component as follows:

```javascript
const Banner = () => {
  return(
    <>
      <Heading border={true}>Styled h1 with a border</Heading>
      <Heading>Styled h1 without a border</Heading>
    </>
  );
}

export default Banner;
```
