1. What would happen if we added one more cookie to our `cookies` array?

   ```javascript
   {
     name: "Katakeet Cookie",
     price: 7,
     image:
       "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fassets.marthastewart.com%2Fstyles%2Fwmax-750%2Fd34%2Feaster-chick-egg-cookies-102921707%2Feaster-chick-egg-cookies-102921707_horiz.jpg%3Fitok%3DUBZfwNLI"
   }
   ```

2. Nothing happened. We need to hard-code the new cookie in JSX. And what if we deleted one of the other cookies? We'll get an error! Is this convenient? How can the user add or delete cookies?

3. To solve this, we need to iterate over our `cookies` and create a new array of the cookie data in JSX. What iteration method can we use to iterate over an array, modify it and save the modified elements in a new array? The answer is `map`.

   ```jsx
   function App(){
     const cookieList = cookies.map(cookie => ())
     return (
       [...]
     )
   }
   ```

4. For now, let's start with returning the name of the cookie only and render it.

   ```jsx
   function App() {
     const cookieList = cookies.map((cookie) => <p>{cookie.name}</p>);
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
           {cookieList}
         </div>
         [...]
       </div>
     );
   }
   ```

5. It worked! Now instead of just returning `cookie.name`, let's return the whole cookie section!

   ```jsx
   const cookieList = cookies.map((cookie) => (
     <div style={styles.cookie}>
       <img
         style={styles.cookieImage}
         alt={cookies[0].name}
         src={cookies[0].image}
       />
       <p style={styles.text}>{cookies[0].name}</p>
       <p style={styles.text}>{cookies[0].price} KD</p>
     </div>
   ));
   ```

6. Let's remove the cookie items from the return and replace them with `cookieList`:

   ```jsx
   <div style={styles.list}>{cookieList}</div>
   ```

7. But now it's only rendering the first cookie, that's because we must replace `cookies[0]` with `cookie` which represents every cookie in our array.

   ```jsx
   const cookieList = cookies.map((cookie) => (
     <div style={styles.cookie}>
       <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
       <p style={styles.text}>{cookie.name}</p>
       <p style={styles.text}>{cookie.price} KD</p>
     </div>
   ));
   ```

8. Yay! Our new cookie is added! Let's open the console, we got a warning ladies and gentlemen:

   `Warning: Each child in a list should have a unique "key" prop.`

9. Now in general we can ignore warnings, but this warning will give us issues later on. Basically, when we save JSX elements in an array, `React` needs to a unique `key` for every element. This key must be added to the parent tag as an attribute, but what will the unique value be?

   ```jsx
   const cookieList = cookies.map((cookie) => (
     <div style={styles.cookie} key={}>
       <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
       <p style={styles.text}>{cookie.name}</p>
       <p style={styles.text}>{cookie.price} KD</p>
     </div>
   ));
   ```

10. Let's take a look at the `cookies` array, the name and image are unique values. But we need something more reliable, so we will add a field called `id` which is a unique that will never be repeated.

    ```javascript
    const cookies = [
      {
        id: 1,
        name: "Chocolate Chip Cookie",
        price: 10,
        image:
          "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg",
      },
      {
        id: 2,
        name: "Cute Cookie",
        price: 15,
        image:
          "https://i.pinimg.com/originals/f6/3e/2a/f63e2a1cd0c7d3c0ab9cd277d3f32050.jpg",
      },
      {
        id: 3,
        name: "Katakeet Cookie",
        price: 7,
        image:
          "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fassets.marthastewart.com%2Fstyles%2Fwmax-750%2Fd34%2Feaster-chick-egg-cookies-102921707%2Feaster-chick-egg-cookies-102921707_horiz.jpg%3Fitok%3DUBZfwNLI",
      },
    ];

    export default cookies;
    ```

11. Now we can access the `id` through `cookie.id` in `map`.

    ```jsx
    const cookieList = cookies.map((cookie) => (
      <div style={styles.cookie} key={cookie.id}>
        <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
        <p style={styles.text}>{cookie.name}</p>
        <p style={styles.text}>{cookie.price} KD</p>
      </div>
    ));
    ```