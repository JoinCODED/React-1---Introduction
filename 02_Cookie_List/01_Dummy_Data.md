At this point there is nothing really special about what we built. We can easily build it with HTML and CSS. Also the code is very bulky and repetitive, it's hard to understand what's going on.


Let's take a look at the list of cookies. We can see that they all have a name, image and price. So why not put the data in an array of objects? Let's try it out.

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
         name: "Cute Cookie",
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
   <div style={styles.cookie}>
     [...]
     <p style={styles.text}>cookies[0].name</p>
     <p style={styles.text}>10 KD</p>
   </div>
   ```

4. Oops.. the cookie name was not rendered. What did we say about rendering JavaScript inside JSX? It must be wrapped in curly brackets.

   ```jsx
   <p style={styles.text}>{cookies[0].name}</p>
   ```

5. Let's apply this to the other fields

   ```jsx
   <div style={styles.cookie}>
     <img
       style={styles.cookieImage}
       alt={cookies[0].name}
       src={cookies[0].image}
     />
     <p style={styles.text}>{cookies[0].name}</p>
     <p style={styles.text}>{cookies[0].price} KD</p>
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
   <div style={styles.cookie}>
     <img
       style={styles.cookieImage}
       alt={cookies[1].name}
       src={cookies[1].image}
     />
     <p style={styles.text}>{cookies[1].name}</p>
     <p style={styles.text}>{cookies[1].price} KD</p>
   </div>
   ```

8. Since this array represents our data, let's move it to its own file and import it. Create a `cookies.js` file inside the `src` folder and move your array there.

9. To import this array we need to export it first:

   ```javascript
   const cookies = [
     {
       name: "Chocolate Chip Cookie",
       price: 10,
       image:
         "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg",
     },
     {
       name: "Cute Cookie",
       price: 15,
       image:
         "https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg",
     },
     {
       name: "Katakeet Cookie",
       price: 7,
       image:
         "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fassets.marthastewart.com%2Fstyles%2Fwmax-750%2Fd34%2Feaster-chick-egg-cookies-102921707%2Feaster-chick-egg-cookies-102921707_horiz.jpg%3Fitok%3DUBZfwNLI",
     },
   ];

   export default cookies;
   ```

10. Now in `App.js`, we can easily import it.

    ```javascript
    import cookies from "./cookies";
    ```

    _Note that we didn't have to mention that this is a javascript file. That's because Javascript files assume that imported files are JavaScript files unless mentioned otherwise._

11. Let's do the same to the `styles` object. Create a file called `styles.js` inside `src`, move the `styles` and export it. I'll add a background color to the background, just because I'm not a fan of pure white backgrounds.

    ```javascript
    const styles = {
      body: { backgroundColor: "#FBFEFC" },
      cookie: { margin: "20px" },
      cookieImage: { width: "200px", height: "200px" },
      list: {
        alignItems: "center",
        justifyContent: "center",
        display: "flex",
      },
      shopImage: {
        display: "block",
        marginLeft: "auto",
        marginRight: "auto",
        width: "50%",
      },
      text: { textAlign: "center" },
    };

    export default styles;
    ```

12. Import it in `App.js`:

    ```javascript
    import styles from "./styles";
    ```

13. Since our imports are increasing, let's organize them by adding comments:

    ```javascript
    import React from "react";

    // Data
    import cookies from "./cookies";

    // Styling
    import styles from "./styles";
    ```