# Add Vitest To A React Project

__Category: React__

Vitest is a test runner and alternative to Jest. This TIL assumes you have created your React project using Vite.

Add Vitest and React Testing Library to your dev dependencies:

```shell
pnpm add -D vitest jsdom @testing-library/react @testing-library/jest-dom
```

Edit `vite.config.ts` to add the following to add `reference` types to top of the file, and the `test` block containing `jsdom` for testing:

```javascript
/// <reference types="vitest" />
/// <reference types="vite/client" />

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react-swc'
import * as path from 'path'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  test: {
    globals: true,
    environment: 'jsdom',
  },
  // etc...
})
```

Add a `test` script to `package.json`:

```json
"scripts": {
  "dev": "vite",
  "build": "tsc && vite build",
  "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0",
  "preview": "vite preview",
  "test:unit": "vitest"
},
```

__Note:__ Tests should reside in a directory called `__tests__`.

Create a test for your component in a file called `Button.test.tsx`. This assumes a component called "Button":

```javascript
import {describe, expect, test} from 'vitest';
import {render, screen} from '@testing-library/react';
import Button from '@components/Button';

describe('Button test', () => {
    test('should show child components', () => {        
        render(<Button label='Testing' onClick={() => console.log('Click')}><h4>Content</h4></Button>);
        expect(screen.getByText(/Content/i)).toBeDefined();
    })
})
```

Run tests:

```shell
pnpm run test:unit
```

Sample output:

```shell
RERUN  src/components/__tests__/Button.test.tsx x1

 ✓ src/components/__tests__/Button.test.tsx (1)
   ✓ Button test (1)
     ✓ should show child components

 Test Files  1 passed (1)
      Tests  1 passed (1)
   Start at  15:16:40
   Duration  269ms


 PASS  Waiting for file changes...
       press h to show help, press q to quit
```
