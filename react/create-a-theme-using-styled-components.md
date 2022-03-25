# Create A Theme Using Styled Components

__Category: React__

You can create themes in styled-components by exporting a `ThemeProvider` wrapper component. This example will create a light and dark theme for a React app using TypeScript conventions.

Create the `theme.ts` file:

```javascript
export interface ThemeType {
  body: string;
  text: string;
}

export const lightTheme: ThemeType = {
  body: '#f1f1f1',
  text: '#121620'
};

export const darkTheme: ThemeType = {
  body: '#121620',
  text: '#f1f1f1'
};

```

Create styles in a `globalStyles.ts` file:

```javascript
import { createGlobalStyle } from 'styled-components';
import { ThemeType } from './theme';

export const GlobalStyles = createGlobalStyle<{theme: ThemeType}>`
  body {
    background: ${({ theme }) => theme.body};
    color: ${({ theme }) => theme.text};
    transition: 0.2s ease-in, color 0.2s ease-in;
  }
  *{
    margin: 0;
    padding: 0;
    outline:0;
    box-sizing:border-box;
    font-family: 'Open Sans', sans-serif; 
  }
  #root{
    margin:0 auto;
  }
`;
```

Reference the theme variables in `styles.ts` files:

```javascript
import styled from 'styled-components';

export const Header = styled.div`
  color: ${({ theme }) => theme.text};
  font-size: 36px;
  letter-spacing: 0.1rem;
  font-weight: 900;
`
```

Use theming by wrapping components in a `ThemeProvider`. If the value for darkMode is true, the application will render components defined in the theme using the darkTheme. If the value for darkMode is false, the application will render body and text components defined in the theme using the lightTheme.

```javascript
import React from 'react';

import { ThemeProvider } from 'styled-components';
import Metrics from './components/metrics';
import { darkModeAtom } from './atoms/darkModeAtom';
import { GlobalStyles } from './styles/globalStyles';
import { lightTheme, darkTheme } from './styles/theme';
import { useRecoilState } from 'recoil';

const Dashboard:React.FC = () => {
  const [darkMode] = useRecoilState(darkModeAtom);
  
  return (
    <ThemeProvider theme={darkMode ? darkTheme : lightTheme}>
      <GlobalStyles/>
      <Metrics/>
    </ThemeProvider>
  );
}

export default Dashboard;
```
