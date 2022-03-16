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
   import CookieList from './components/CookieList';
   import Home from './components/Home';
   ```

5. Render it under `Home`.

   ```jsx
     return (
       <div className="body">
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
     return <div className="list">{cookieList}</div>;
   };
   ```

7. We got one error: `'cookieList' is not defined`

8. We need to move our `cookieList` variable from `App.js`:

   ```javascript
   const CookieList = () => {
     const cookieList = cookiesData.map((cookie) => (
       <div className="cookie">
         <img className="cookie-image" alt={cookie.name} src={cookie.image} />
         <p className="text">{cookie.name}</p>
         <p className="text">{cookie.price} KD</p>
       </div>
     ));
     return <div className="list">{cookieList}</div>;
   };
   ```

9. We got another error: `'cookiesData' is not defined`.

10. We need to import `cookiesData` as well in `CookieList.js`.

    ```javascript
    // Data
    import cookiesData from '../cookies';
    ```

11. Let's check our website, nothing changed. Which means that this worked!
