1. In `App.js` import the `styled` method from `styled-components`. We will create our styled components in `App.js` then move them to `styles`.

   ```javascript
   import styled from "styled-components";
   ```

2. I want to create a styled component for my title, so I'll give it the name `Title`. Since it's a component, it **must** start with a capital letter. To create a styled component we will use `styled` followed by the element type, our title uses the element `h1`.

   ```javascript
   import styled from "styled-components";

   const Title = styled.h1;
   ```

3. Then we will add two back-ticks ``and inside them we can write our CSS! Let's give our title some style! So we created a component called`Title`that has all the styling properties of an`h1` tag **plus** the styling we added.

   ```javascript
   const Title = styled.h1`
     text-align: center;
     color: purple;
   `;
   ```

4. To use this component `Title`, we will remove the `h1` tag wrapping `Cookies and Beyond` and replace it with `Title`.

   ```jsx
   <Title>Cookies and Beyond</Title>
   ```

5. Let's check our browser. How cool is this?! And our component is much cleaner now. One more thing, if we check our react dev tool, you'll see that `styled.h1` is included in the components tree, which will make tracking styling much easier!

6. Let's create a styled component for our description.

   ```javascript
   const Description = styled.h4`
     text-align: center;
   `;
   ```

7. Now let's replace the `h4` with `Description`:

   ```jsx
   <Description>Where cookie maniacs gather</Description>
   ```

8. Let's create a styled component for our image. I'll copy the style from `styles.shopImage` and convert it to CSS.

   ```javascript
   const ShopImage = styled.img`
     display: block;
     margin-left: auto;
     margin-right: auto;
     width: 50%;
   `;
   ```

9. For the image, `ShopImage` will be a self-closing tag and we will pass it `src` and `alt`.

   ```jsx
   <ShopImage
     alt="cookie shop"
     src="https://i.pinimg.com/originals/8f/cf/71/8fcf719bce331fe39d7e31ebf07349f3.jpg"
   />
   ```
