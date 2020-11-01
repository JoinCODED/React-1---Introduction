Let's add a list of cookies to our page right under the cookie shop image.

1. First I'll add a `<div>` tag to wrap the list of cookies, and another `<div>` to wrap our two `<div>` tags as a parent.

   ```jsx
   <div>
     <div>
       <h1 style={styles.text}>Cookies and Beyond</h1>
       <h4 style={styles.text}>Where cookie maniacs gather</h4>
       <img
         alt="cookie shop"
         src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
         style={styles.shopImage}
       />
     </div>
     <div></div>
   </div>
   ```

2. Let's add our first cookie, a chocolate chip cookie. We'll give every cookie an image, name and price:

   ```jsx
   <div>
     <img
       alt="chocolate chip cookie"
       src="https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
     />
     <p>Chocolate Chip Cookie</p>
     <p>10 KD</p>
   </div>
   ```

3. Let's style it a bit by giving every image a height and width and centering the text. In our `styles` object, we'll add a new styling object for the cookie image and we'll apply `text` style to the name and price.

   ```javascript
   const styles = {
     text: { textAlign: "center" },
     shopImage: {
       display: "block",
       marginLeft: "auto",
       marginRight: "auto",
       width: "50%",
     },
     cookieImage: { width: "200px", height: "200px" },
   };
   ```

4. Let's apply it on our cookie:

   ```jsx
   <div>
     <img
       alt="chocolate chip cookie"
       src="https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg"
       style={styles.cookieImage}
     />
     <p style={styles.text}>Chocolate Chip Cookie</p>
     <p style={styles.text}>10 KD</p>
   </div>
   ```

5. Then we'll just copy and paste this block of code to display one more cookie:

   ```jsx
   <div>
     <img
       alt="cute cookie"
       src="https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg"
       style={styles.cookieImage}
     />
     <p style={styles.text}>Cute Cookie</p>
     <p style={styles.text}>8 KD</p>
   </div>
   ```

6. But the design is awful. Let's fix it by styling the `div` tag that's wrapping all three cookies:

   ```javascript
   const styles = {
     ...
     list: {
       alignItems: "center",
       justifyContent: "center",
       display: "flex"
     }
   };
   ```

   And apply the styles:

   ```jsx
   return (
     <div>
       <div>...</div>
       <div style={styles.list}>...</div>
     </div>
   );
   ```

7. Also, for every cookie `div` we will add a margin to make some space between them.

   ```javascript
   const styles = {
     ...
     list: {
       alignItems: "center",
       justifyContent: "center",
       display: "flex"
     },
     cookie: { margin: "20px" }
   };
   ```

   And apply the styles:

   ```jsx
   return (
     <div>
       <div>...</div>
       <div style={styles.list}>
         <div style={styles.cookie}>...</div>
         <div style={styles.cookie}>...</div>
       </div>
     </div>
   );
   ```

And there you have it! A beautifully designed cookie list page!
