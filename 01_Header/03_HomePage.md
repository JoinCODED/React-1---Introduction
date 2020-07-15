1. Let's start with adding a title for our website:

   ```jsx
   function App() {
     return <h1>Cookies and Beyond</h1>;
   }
   ```

2. Note that when we save our code, the website is automatically updated! And that ladies and gentlemen is the first super power of React.

3. Now let's add a description of our website under the title:

   ```jsx
   function App() {
     return (
       <h1>Cookies and Beyond</h1>
       <h4>Where cookie maniacs gather</h4>
     );
   }
   ```

4. Oops! We got an error. But why? Let's read the error.

   ```
   Parsing error: Adjacent JSX elements must be wrapped in an enclosing tag.
   ```

5. Another difference between JSX and HTML. We can't have two tags without a parent tag. So we will wrap those two tags with a `div` tag:

   ```jsx
   return (
     <div>
       <h1>Cookies and Beyond</h1>
       <h4>Where cookie maniacs gather</h4>
     </div>
   );
   ```

6. Now let's add an image of a cookie shop, so we will use an `img` tag. For now, we will take our images from the internet. Choose your image, copy its address and paste it in the `src` attribute. Don't forget to add alternative text using the `alt` attribute.

   ```jsx
   return (
     <div>
       <h1>Cookies and Beyond</h1>
       <h4>Where cookie maniacs gather</h4>
       <img
           alt="cookie shop"
           src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
       >
     </div>
   );
   ```

7. We got another error:

   ```
   Parsing error: Unterminated JSX contents
   ```

8. In HTML, the `/` at the end of a self-closing tag is optional, but in JSX it's mandatory.

   ```jsx
   return (
     <div>
       <h1>Cookies and Beyond</h1>
       <h4>Where cookie maniacs gather</h4>
       <img
         alt="cookie shop"
         src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
       />
     </div>
   );
   ```