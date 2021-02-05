# Extending Styled Components

__Category: React__

Extending a styled component can reduce the amount of boilerplate code needing to be written. 

You can also override styles in the extending styled component.

```javascript
const MainContainer = styled.div`
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
`;

const MainContainerExtended = styled(MainContainer)`
  flex-direction: column-reverse;
`;
```
