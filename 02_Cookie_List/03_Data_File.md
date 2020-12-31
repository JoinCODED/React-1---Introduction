1. Since the cookies array represents our data, let's move it to its own file and import it. Create a `cookies.js` file inside the `src` folder and move your array there.

2. To import this array we need to export it first:

   ```javascript
   const cookiesData = [
     {
       name: "Chocolate Chip Cookie",
       price: 10,
       image:
         "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg",
     },
     {
       name: "Adorable Cookie",
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

   export default cookiesData;
   ```

3. Now in `App.js`, we can easily import it.

   ```javascript
   import cookiesData from "./cookies";
   ```

   _Note that we didn't have to mention that this is a javascript file. That's because Javascript files assume that imported files are JavaScript files unless mentioned otherwise._

4. Let's do the same to the `styles` object. Create a file called `styles.js` inside `src`, move the `styles` and export it. I'll add a color to the background, just because I'm not a fan of pure white backgrounds.

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

5. Import it in `App.js`:

   ```javascript
   import styles from "./styles";
   ```

6. Since our imports are increasing, let's organize them by adding comments:

   ```javascript
   import React from "react";

   // Data
   import cookiesData from "./cookies";

   // Styling
   import styles from "./styles";
   ```
