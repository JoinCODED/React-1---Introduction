This is when we introduce a very powerful super power of React called `props`.

1. Let's comment out the JSX in `CookieItem` and `CookieList`, and `cookieList` in `CookieList` first to try things out.

2. Let's say I want to pass the string `Chocolate Cookie` to `CookieItem` and render it. We will treat it the same way we give a tag an attribute, a name and value. You're free to call it whatever you want, we called it `name` since it represents the name of the cookie, and the value will be our string `Chocolate Cookie`.

   ```javascript
   return (
     <div style={styles.list}>
       {/* {cookieList} */}
       <CookieItem name="Chocolate Cookie" />
     </div>
   );
   ```

This process is called passing `Chocolate Cookie` as a prop.

3. But how can we access `name` in `CookieItem`? Now is the time to make use of the React Dev Tools. Let's take a look at it. Click on `component`, then click on `CookieItem`. On the right side you'll see something called `props`, which is an object that has `name`.

4. Let's try to console log it in our component:

   ```javascript
   const CookieItem = () => {
     console.log(props);
     return (
       <div style={styles.cookie} key={cookie.id}>
         {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
         <p style={styles.text}>{cookie.name}</p>
         <p style={styles.text}>{cookie.price} KD</p> */}
       </div>
     );
   };
   ```

5. Ughh, the same error again! `'props' is not defined`.

6. Basically to use `props` we need to pass it as an argument to `CookieItem`.

   ```javascript
   const CookieItem = (props) => {
     console.log(props);
   };
   ```

7. And we got our `props` object! So we can render `Chocolote Cookie` now! Yaay!

   ```javascript
   const CookieItem = () => {
     console.log(props);
     return (
       <div style={styles.cookie} key={cookie.id}>
         <p>{props.name}</p>
         {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
         <p style={styles.text}>{cookie.name}</p>
         <p style={styles.text}>{cookie.price} KD</p> */}
       </div>
     );
   };
   ```

8. What if I want to pass more than one item as a prop, the price for example? Easy. You basically add it with a space between it and the other prop. Keep in mind that **all** values must be in curly brackets except strings, which are placed in quotations.

   ```jsx
   <CookieItem name="Chocolate Cookie" price={6} />
   ```

9. Let's take a look at the dev tools. You'll see that price is added to the `props` object!

10. We can easily access it through props!

    ```javascript
    const CookieItem = () => {
      console.log(props);
      return (
        <div style={styles.cookie} key={cookie.id}>
          <p>{props.name}</p>
          <p>{props.price}</p>
          {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
          <p style={styles.text}>{cookie.name}</p>
          <p style={styles.text}>{cookie.price} KD</p> */}
        </div>
      );
    };
    ```

11. Let's pass an image as a prop as well!

    ```jsx
    <CookieItem
      name="Chocolate Cookie"
      price={6}
      image="https://www.meals.com/imagesrecipes/144807lrg.jpg"
    />
    ```

12. And let's render it in `CookieItem`.

    ```javascript
    const CookieItem = () => {
      console.log(props);
      return (
        <div style={styles.cookie} key={cookie.id}>
          <p>{props.name}</p>
          <p>{props.price}</p>
          <img src={props.image} />
          {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
          <p style={styles.text}>{cookie.name}</p>
          <p style={styles.text}>{cookie.price} KD</p> */}
        </div>
      );
    };
    ```

13. But our `<CookieList />` is becoming bulky. Don't worry, props are amazing, you can literally send **anything** through it. So let's create an object in `CookieList` and pass it as a prop to `CookieItem`!

    ```javascript
    const CookieList = () => {
      // const cookieList = cookiesData.map((cookie) => (
      //   <CookieItem cookie={cookie} />
      // ));
      const cookie = {
        name: "Chocolate Cookie",
        price: 7,
        image: "https://www.meals.com/imagesrecipes/144807lrg.jpg",
      };
      return (
        <div style={styles.list}>
          {/* {cookieList} */}
          <CookieItem cookie={cookie} />
        </div>
      );
    };
    ```

14. Let's check the dev tools. We'll see that there is an object called `cookies` inside `props`. So how can we access the properties of `cookie`? Through `props.cookie`.

    ```jsx
    return (
      <div style={styles.cookie}>
        <p>{props.cookie.name}</p>
        <p>{props.cookie.price}</p>
        <img src={props.cookie.image} />
        {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
          <p style={styles.text}>{cookie.name}</p>
          <p style={styles.text}>{cookie.price} KD</p> */}
      </div>
    );
    ```

15. It's annoying how `props.cookie` is repeated every time we need one of this fields. so we create a variable called `cookie` that is equal to the object `props.cookie`, it makes things much cleaner.

    ```javascript
    const CookieItem = props => {
      const cookie = props.cookie;
      return (
        <div style={styles.cookie}>
          <p>{cookie.name}</p>
          <p>{cookie.price}</p>
          <img src={cookie.image} />
          {/* <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
            <p style={styles.text}>{cookie.name}</p>
            <p style={styles.text}>{cookie.price} KD</p> */}
        </div>
      );
    ```

16. I believe we can use our original code now!

    ```javascript
    const CookieItem = props => {
      const cookie = props.cookie;
      return (
        <div style={styles.cookie}>
            <img style={styles.cookieImage} alt={cookie.name} src={cookie.image} />
            <p style={styles.text}>{cookie.name}</p>
            <p style={styles.text}>{cookie.price} KD</p>
        </div>
      );
    ```

17. And we got our design back! But now we want our cookies from `cookies` array! So let's pass every cookie to a `CookieItem` instance.

    ```javascript
    const CookieList = () => {
      return (
        <div style={styles.list}>
          <CookieItem cookie={cookiesData[0]} />
          <CookieItem cookie={cookiesData[1]} />
          <CookieItem cookie={cookiesData[2]} />
        </div>
      );
    };
    ```

    The problem is that how can my code know how many cookies I have in my array? That's why instead of re-rendering `CookieItem` manually, we use a `.map` which will create an array of `CookieItem` components with a different `cookie` for every element in the array.

18. So we will pass `cookie` -which represents a different cookie object in every iteration- as a prop.

    ```javascript
    const CookieList = () => {
      const cookieList = cookiesData.map(cookie => (
        <CookieItem cookie={cookie} />
      ));
    ```

    Let's open the console, we got a warning ladies and gentlemen:

    `Warning: Each child in a list should have a unique "key" prop.`

19. Now in general we can ignore warnings, but this warning will give us issues later on. Basically, when we save JSX elements in an array, `React` needs to have a unique `key` for every element. This key must be added to the parent tag as an attribute, but what will the unique value be?

    ```jsx
    const cookieList = cookiesData.map((cookie) => (
      <CookieItem cookie={cookie} key={} />
    ));
    ```

20. Let's take a look at the `data` array, the name and image are unique values. But we need something more reliable, so we will add a field called `id` which is a unique that will never be repeated.

    ```javascript
    const data = [
      {
        id: 1,
        name: "Chocolate Chip Cookie",
        price: 10,
        image:
          "https://joyfoodsunshine.com/wp-content/uploads/2016/01/best-chocolate-chip-cookies-recipe-ever-no-chilling-1.jpg",
      },
      {
        id: 2,
        name: "Adorable Cookie",
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

    export default data;
    ```

21. Now we can access the `id` through `cookie.id` in the `.map()`.

    ```jsx
    const cookieList = cookiesData.map((cookie) => (
      <CookieItem cookie={cookie} key={cookie.id} />
    ));
    ```

22. Keep in mind that `key` can't be used, it's for the code not for us. If you take a look at the dev tools, you'll see that `key` is not in the `props` object, so we have no access to it.
