1. Let's take a look at the JSX in the `.map` in `CookieList`. This should be its own component. Let's create it.

2. In `components`, we will create a file called `CookieItem.js`.

3. Then, we will create our component function `CookieItem`.

   ```javascript
   const CookieItem = () => {};
   ```

4. Let's move in the cookie JSX from `CookieList.js`.

   ```javascript
   const CookieItem = () => {
     return (
       <div style={styles.cookie}>
         <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
         <p style={styles.text}>{cookie.name}</p>
         <p style={styles.text}>{cookie.price} KD</p>
       </div>
     );
   };
   ```

5. We also need to import `styles`.

   ```javascript
   // Styling
   import styles from "../styles";
   ```

6. Let's not forget to export the component at the bottom of the file.

   ```javascript
   export default CookieItem;
   ```

7. In `CookieList.js`, import `CookieItem`.

   ```javascript
   // Components
   import CookieItem from "./CookieItem";
   ```

8. We will render `CookieItem` in the `map` method.

   ```javascript
   const cookieList = cookiesData.map((cookie) => <CookieItem />);
   ```

9. And we got an error! `'cookie' is not defined`. But how can we pass `cookie` from the `map` method in `CookieList` to `CookieItem`? Especially that `cookie` represents a different cookie through the iteration, every instance of `CookieItem` needs a different `cookie`!
