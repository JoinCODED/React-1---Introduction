[React 3 - Components and Props](https://docs.google.com/presentation/d/1VhahKb_U-eNWm488M4Ea0u5GgR3-BqnAGB0v5hvW2IU/edit#slide=id.g89fc9bce5c_1_0)

At this point, all of our code is in `App.js`. But what will happen when our website becomes bigger? Basically, we will split the code in `App.js` to many components.


1. First, we will create a folder called `components`. This is where we will place all our components **except** `App.js`.

2. Now in `components`, we will create a file called `CookieList.js`.

3. The first step in creating a component is importing `React`.

```javascript
import React from "react";
```

4. Then, we will create a function -which is our component- called `CookieList`. The component **must** start with a capital letter, otherwise it will cause you issues.

```javascript
import React from "react";

const CookieList = () => {};
```

5. The return value of this function is the JSX that will be rendered on the screen when `CookieList` is called. For now let's add any message to it.

```javascript
import React from "react";

const CookieList = () => {
  return <h1>I'm the CookieList component!</h1>;
};
```

6. To use this component in `App.js`, we will need to import it. And you can't import something if it's not exported.

```javascript
import React from "react";

const CookieList = () => {
  return <h1>I'm the CookieList component!</h1>;
};

export default CookieList;
```

7. In `App.js`, import `CookieList`. Regarding the path, for `App.js` to reach `CookieList.js`, it has to go inside `components` folder and to `CookieList.js` to import it. Since `App.js` and `components` are in the same directory the path will start with `./` followed by the `components` which is the directory we want to go to followed by `CookieList` which is the file we want to reach into.

```javascript
import React from "react";

// Components
import CookieList from "./components/CookieList";
```

8. Now how can we render `CookieList`? Any guesses?

9. To render a component, we will wrap it in a tag.

```jsx
  return (
    <div style={styles.body}>
        <div>...</div>
        <CookieList />
    <div>
  )
```

Tada!!! It worked! Easy right?

10. Can we call a component more than once? Yes, you can call it as many times as you want! Let's call `<CookieList />` many times. Basically every time we render a component we are creating an **instance** of this component.

```jsx
function App() {
  return (
    <div style={styles.body}>
        <div>...</div>
        <CookieList />
        <CookieList />
        <CookieList />
        <CookieList />
      <div>
```

Nice! Let's remove them now.

11. Let's move our cookie list to the `CookieList` component.

```jsx
const CookieList = () => {
  return <div style={styles.list}>{cookieList}</div>;
};
```

12. We got two errors: `'styles' is not defined` and `'cookieList' is not defined`

13. We need to import `styles` in `Home.js`! Regarding the path, this time `Home.js` wants to access `styles.js` which is outside the `components` folder, so `Home.js` must leave `components` to reach `styles.js`. To reach for a higher directory the path will start `../` followed by `styles` which is the file we need to access.

```javascript
import React from "react";

// Styling
import styles from "../styles";
```

14. We also need to move `cookieList` from `App.js`:

```javascript
const CookieList = () => {
  const cookieList = cookies.map((cookie) => (
    <div style={styles.cookie} key={cookie.id}>
      <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
      <p style={styles.text}>{cookie.name}</p>
      <p style={styles.text}>{cookie.price} KD</p>
    </div>
  ));
  return <div style={styles.list}>{cookieList}</div>;
};
```

15. We got another error: `'cookies' is not defined`.

16. We need to import `cookies` too.

```javascript
import React from "react";

// Data
import cookies from "../cookies";
```

17. Let's check our website, nothing changed. Which means that this worked!
