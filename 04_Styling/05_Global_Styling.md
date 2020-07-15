What if we have styling that we want to apply to the whole application? For example, I want to change the background color and the main font color.

1. Basically we will create a global styling using `createGlobalStyle`, which we import from `styled-components` in `styles.js`.

```javascript
import styled, { createGlobalStyle } from "styled-components";
```

2. Next we define our variable, I'll call it `GlobalStyle` and it's equal to the return value of `createGlobalStyle` which is followed by back-ticks ``.

```javascript
const GlobalStyle = createGlobalStyle`
  
`;
```

3. Keep in mind that this styling should NOT be abused, only use it for cases like styling the `body` or globalizing a font. In our case, we will define the main color and background color:

```javascript
const GlobalStyle = createGlobalStyle`
  body {
    color: #242424;
    background-color: #fefafb
  }
`;
```

4. Export `GlobalStyle` and import it in `App.js`

```javascript
export {
  CookieWrapper,
  Description,
  GlobalStyle,
  ListWrapper,
  Title,
  ShopImage,
};
```

5. Call `GlobalStyle` right under your first `div` tag:

```jsx
  <div>
    <GlobalStyle />
```

6. Let's inspect our website. Yes! The background and font colors changed in all our application!
