At this point, all of our code is in `App.js`. But what will happen when our website becomes bigger? Basically, we will split the code in `App.js` to many components.

1. First, we will create a folder called `components`. This is where we will place all our components **except** `App.js`.

2. Now in `components`, we will create a file called `Home.js`.

3. In `Home.js`, we will create a function -which is our component- called `Home`. The component **must** start with a capital letter, otherwise it will cause you issues.

   ```javascript
   const Home = () => {};
   ```

4. The return value of this function is the JSX that will be rendered on the screen when `Home` is called. For now let's add any message to it.

   ```javascript
   const Home = () => {
     return <h1>I'm the Home component!</h1>;
   };
   ```

5. To use this component in `App.js`, we will need to import it. And you can't import something if it's not exported.

   ```javascript
   const Home = () => {
     return <h1>I'm the Home component!</h1>;
   };

   export default Home;
   ```

6. In `App.js`, import `Home`. Regarding the path, for `App.js` to reach `Home.js`, it has to go inside `components` folder and to `Home.js` to import it. Since `App.js` and `components` are in the same directory the path will start with `./` followed by the `components` which is the directory we want to go to followed by `Home` which is the file we want to reach into.

   ```javascript
   // Components
   import Home from './components/Home';
   ```

7. Now how can we render `Home`? Any guesses?

8. To render a component, we will wrap it in a tag.

   ```jsx
   return (
       <div className="body">
           <div>...</div>
           <Home />
       <div>
   )
   ```

   Tada!!! It worked! Easy right?

9. Can we call a component more than once? Yes, you can call it as many times as you want! Let's call `<Home />` many times. Basically every time we render a component we are creating an **instance** of this component.

   ```jsx
   function App() {
   return (
       <div className="body">
           <div>...</div>
           <Home />
           <Home />
           <Home />
           <Home />
       <div>
   ```

Nice! Let's remove them now.

11. Let's move our title, description and image to the `Home` component.

    ```jsx
    const Home = () => {
      return (
        <div>
          <h1 className="text">Cookies and Beyond</h1>
          <h4 style="text">Where cookie maniacs gather</h4>
          <img
            alt="cookie shop"
            src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
            style="shop-image"
          />
        </div>
      );
    };
    ```
