Let's also create a component for our list of cookies.

1. Now in `components`, we will create a file called `CookieList.js`.

2. Then, we will create our function, `CookieList`.

   ```javascript
   const CookieList = () => {};
   ```

3. The return value of this function is the JSX that will be rendered on the screen when `CookieList` is called. For now let's add any message to it and export it.

   ```javascript
   const CookieList = () => {
     return <h1>I'm the CookieList component!</h1>;
   };

   export default CookieList;
   ```

4. In `App.js`, import `CookieList`.

   ```javascript
   // Components
   import CookieList from "./components/CookieList";
   import Home from "./components/Home";
   ```

5. Render it under `Home`.

   ```jsx
     return (
       <div style={styles.body}>
           <div>...</div>
           <Home />
           <CookieList />
       <div>
     )
   ```

   Tada!!! It worked!

6. Now let's move our cookie list to the `CookieList` component.

   ```jsx
   const CookieList = () => {
     return <div style={styles.list}>{cookieList}</div>;
   };
   ```

7. We got two errors: `'styles' is not defined` and `'cookieList' is not defined`

8. We need to import `styles` in `CookieList.js`.

   ```javascript
   // Styling
   import styles from "../styles";
   ```

9. We also need to move our `cookieList` variable from `App.js`:

   ```javascript
   const CookieList = () => {
     const cookieList = cookies.map((cookie) => (
       <div style={styles.cookie}>
         <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
         <p style={styles.text}>{cookie.name}</p>
         <p style={styles.text}>{cookie.price} KD</p>
       </div>
     ));
     return <div style={styles.list}>{cookieList}</div>;
   };
   ```

10. We got another error: `'cookies' is not defined`.

11. We need to import `cookies` as well in `CookieList.js`.

    ```javascript
    // Data
    import cookies from "../cookies";

    // Styling
    import styles from "../styles";
    ```

12. Let's check our website, nothing changed. Which means that this worked!
