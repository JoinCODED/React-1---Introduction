1. Our website needs styling! Let's start with centering the title.

   ```jsx
   <h1 style="text-align: center">Cookies and Beyond</h1>
   ```

2. Another proof that this is not HTML. We got another error!

   ```
   Style prop value must be an object
   ```

3. So we must pass an object to `style`. So the styling passed to `style` is actually Javascript and not CSS. This is the biggest difference between HTML and JSX, we can include JavaScript in our JSX code. Note that it's very similar to CSS, but the naming convention is _camelCase_.

   ```jsx
   <h1 style={ textAlign: "center" }>Cookies and Beyond</h1>
   ```

4. But we still got an error, even though we gave style an object.

5. Whenever we use JavaScript inside JSX, we need to wrap it with curly brackets. In this case, we have double curly brackets, one is for JSX and the other is because we're passing an object to `style`.

   ```jsx
   <h1 style={{ textAlign: "center" }}>Cookies and Beyond</h1>
   ```

6. Let's also center the description.

   ```jsx
   <h4 style={{ textAlign: "center" }}>Where cookie maniacs gather</h4>
   ```

7. Now let's center the image. Honestly I don't know how to do that, so let's [google it](https://www.w3schools.com/howto/howto_css_image_center.asp). Any style I need I will look for it in HTML and CSS, then convert it to JavaScript. Let's add the code:

   ```jsx
   style={{
     display: block;
     margin-left: auto;
     margin-right: auto;
     width: 50%;
   }}
   ```

8. To convert it to JSX, fix the keys from kebab-case to camelCase, replace `;` with `,` and change the values to strings.

   ```jsx
   style={{
     display: "block",
     marginLeft: "auto",
     marginRight: "auto",
     width: "50%"
   }}
   ```

9. As you can see, our code is starting to become bulky. So we will create a `styles` object before the `App` function and move all our object styles:

   ```javascript
   const styles = {};

   function App() {
     [...]
   }
   ```

10. Since the title and description have the same style, we can combine them under the key `text`. You're free to give your style objects whatever name you want, just make sure it's clear what this object is doing:

    ```javascript
    const styles = {
      text: { textAlign: "center" },
    };
    ```

11. Let's add the image's styling as well. Since this styling is specific for the shop's image, I'll call it `shopImage`.

    ```javascript
    const styles = {
      text: { textAlign: "center" },
      shopImage: {
        display: "block",
        marginLeft: "auto",
        marginRight: "auto",
        width: "50%",
      },
    };
    ```

12. Now we can replace the objects. Wow! This looks much better.

    ```jsx
    <div>
      <h1 style={styles.text}>Cookies and Beyond</h1>
      <h4 style={styles.text}>Where cookie maniacs gather</h4>
      <img
        alt="cookie shop"
        src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
        style={styles.shopImage}
      />
    </div>
    ```
