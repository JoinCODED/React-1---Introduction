It's getting a bit annoying with the color values, and it will become even more difficult to manage them when our website grows. So we will create a theme and pass it as `props` to all components.

1. In `App.js`, let's create our `theme` object outside the component and add all the colors we'll use in our application. For now these are my colors:

```javascript
const theme = {
  mainColor: "#242424", // main font color
  backgroundColor: "#fefafb", // main background color
  pink: "#ff85a2",
};
```

2. Then, import `ThemeProvider` from `styled-components`. It **must** be between curly brackets.

```javascript
import { ThemeProvider } from "styled-components";
```

3. Then we will wrap our highest element with it and pass it our `theme` object as a prop.

```jsx
<ThemeProvider theme={theme}>
  <>...</>
  <CookieList />
</ThemeProvider>
```

4. Let's check the React Dev Tool. Click on any component, on the right side you'll see that it has access to `theme`. Let's use it!

5. Go to `CookieWrapper` in `styles.js`, but how can we access theme?

6. We'll use a template literal and pass it a function, the argument of this function is `props`, saved inside `props` is `theme`. The template literal is to convert the returned value.

```javascript
&.cookie-price {
      color: ${props => props.theme.pink};
    }
```

7. Amazing! It worked! Let's apply it to `GlobalStyle` as well:

```javascript
const GlobalStyle = createGlobalStyle`
  body {
    color: ${(props) => props.theme.mainColor};
    background-color: ${(props) => props.theme.backgroundColor}
  }
`;
```
