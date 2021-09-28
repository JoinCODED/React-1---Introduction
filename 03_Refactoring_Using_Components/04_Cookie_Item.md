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
       <div className="cookie">
         <img className="cookie-image" alt={cookie.name} src={cookie.image} />
         <p className="text">{cookie.name}</p>
         <p className="text">{cookie.price} KD</p>
       </div>
     );
   };
   ```

5. Let's not forget to export the component at the bottom of the file.

   ```javascript
   export default CookieItem;
   ```

6. In `CookieList.js`, import `CookieItem`.

   ```javascript
   // Components
   import CookieItem from './CookieItem';
   ```

7. We will render `CookieItem` in the `map` method.

   ```javascript
   const cookieList = cookiesData.map((cookie) => <CookieItem />);
   ```

8. And we got an error! `'cookie' is not defined`. But how can we pass `cookie` from the `map` method in `CookieList` to `CookieItem`? Especially that `cookie` represents a different cookie through the iteration, every instance of `CookieItem` needs a different `cookie`!
