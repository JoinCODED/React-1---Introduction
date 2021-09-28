At this point there is nothing really special about what we built. We can easily build it with HTML and CSS. Also the code is very bulky and repetitive, it's hard to understand what's going on.

Let's take a look at the list of cookies. We can see that they all have a `name`, `image` and `price`. So why not put the data in an array of objects? Let's try it out.

1. Create a new array inside the `App` function:

   ```javascript
   function App() {
     const cookies = [
       {
         name: "Chocolate Chip Cookie",
         price: 10,
         image:
           "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
       },
       {
         name: "Adorable Cookie",
         price: 15,
         image:
           "https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg"
       }
     ];
     [...]
    }
   ```

2. How can we access those objects? Let's try `console.log`-ing the first object's name to see:

   ```javascript
   console.log(cookies[0].name);
   ```

   You'll see the `console.log` message in the browser's console. Right-click anywhere on the page, click on `inspect`, then go to the `console` tab.

3. Let's go to our first cookie and replace `Chocolate Chip Cookie` with the cookie from the array:

   ```jsx
   <div className="cookie">
     [...]
     <p className="text">cookies[0].name</p>
     <p className="text">10 KD</p>
   </div>
   ```

4. Oops.. the cookie name was not rendered. What did we say about writing JavaScript inside JSX? It must be wrapped in curly brackets.

   ```jsx
   <p className="text">{cookies[0].name}</p>
   ```

5. Let's apply this to the other fields

   ```jsx
   <div className="cookie">
     <img
       className="cookie-image"
       alt={cookies[0].name}
       src={cookies[0].image}
     />
     <p className="text">{cookies[0].name}</p>
     <p className="text">{cookies[0].price} KD</p>
   </div>
   ```

6. Let's edit our array and change the price of the first cookie just to see what happens to our website.

   ```javascript
   function App() {
     const cookies = [
       {
         name: "Chocolate",
         price: 8,
         image:
           "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
       },
       [...]
     ];
   ```

   Woow it changed!!!

7. Let's also apply this to the other cookie:

   ```jsx
   <div className="cookie">
     <img
       className="cookie-image"
       alt={cookies[1].name}
       src={cookies[1].image}
     />
     <p className="text">{cookies[1].name}</p>
     <p className="text">{cookies[1].price} KD</p>
   </div>
   ```
