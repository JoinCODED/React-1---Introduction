1. What would happen if we added one more cookie to our `cookies` array?

   ```javascript
   {
     name: "Katakeet Cookie",
     price: 7,
     image: "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fassets.marthastewart.com%2Fstyles%2Fwmax-750%2Fd34%2Feaster-chick-egg-cookies-102921707%2Feaster-chick-egg-cookies-102921707_horiz.jpg%3Fitok%3DUBZfwNLI"
   }
   ```

2. Nothing happened. We need to hard-code the new cookie in JSX. And what if we deleted one of the other cookies? We'll get an error! Is this convenient? What if we want the user add or delete cookies?

3. To solve this, we need to iterate over our `cookies` array and create a new array of the cookie data in JSX. What iteration method can we use to iterate over an array, modify it and save the modified elements in a new array? The answer is `.map()`.

   ```jsx
   function App(){
     const cookieList = cookiesData.map(cookie => ())
     return (
       [...]
     )
   }
   ```

4. For now, let's start with returning the name of the cookie only and render it in a `<p>` tag.

   ```jsx
   function App() {
     const cookieList = cookiesData.map((cookie) => <p>{cookie.name}</p>);
     return (
       <div>
         <div style={styles.body}>
           <h1 style={styles.text}>Cookies and Beyond</h1>
           <h4 style={styles.text}>Where cookie maniacs gather</h4>
           <img
             alt="cookie shop"
             src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
             style={styles.shopImage}
           />
         </div>
         <div style={styles.cookieList}>{cookieList}</div>
       </div>
     );
   }
   ```

5. It worked! Now instead of just returning `cookie.name`, let's return the whole cookie section! We must change `cookiesData[0]` to `cookie`.

   ```jsx
   const cookieList = cookiesData.map((cookie) => (
     <div style={styles.cookie}>
       <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
       <p style={styles.text}>{cookie.name}</p>
       <p style={styles.text}>{cookie.price} KD</p>
     </div>
   ));
   ```

6. Let's remove the cookie items from the return and replace them with `cookieList`:

   ```jsx
   <div style={styles.list}>{cookieList}</div>
   ```

7. Yay! Our new cookie is added!
