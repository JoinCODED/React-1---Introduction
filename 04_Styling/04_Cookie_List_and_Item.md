1. Let's move to `CookieList`, I want you all to tell me what the styled component will look like, let's call it `ListWrapper` and copy the styling from `styles.list`.

   ```javascript
   export const ListWrapper = styled.div`
     align-items: center;
     justify-content: center;
     display: flex;
   `;
   ```

2. In `CookieList`, import `ListWrapper` and replace `div` with it

   ```javascript
   // Styling
   import { ListWrapper } from "../styles";
   ```

3. Replace `div` with `ListWrapper`

   ```javascript
   return <ListWrapper>{cookieList}</ListWrapper>;
   ```

4. In `CookieItem`, I'm gonna go for a different approach with styled components. Since we said that styled components uses CSS, let's apply some of the CSS properties we learnt.

5. Let's start with creating a styled component called `CookieWrapper` for the `div` in `CookieItem`, move the style from `styles.cookie` and convert it to CSS.

   ```javascript
   export const CookieWrapper = styled.div`
     margin: 20px;
   `;
   ```

6. Apply the changes in `CookieItem`. Also let's remove the styling coming from `styles`

   ```jsx
   <CookieWrapper>
     <img alt={cookie.name} src={cookie.image} />
     <p>{cookie.name}</p>
     <p>{cookie.price} KD</p>
   </CookieWrapper>
   ```

7. Now `img` and `p` are inside `div`, we don't need to create a styled component for each of them. We can apply a certain style for all `img` and `p` tags inside `CookieWrapper`. Let's start with `img` tag:

   ```javascript
   export const CookieWrapper = styled.div`
     margin: 20px;

     img {
       width: 200px;
       height: 200px;
     }
   `;
   ```

8. How cool is that? Let's style the `p` tag:

   ```javascript
   export const CookieWrapper = styled.div`
     margin: 20px;

     img {
       width: 200px;
       height: 200px;
     }

     p {
       text-align: center;
     }
   `;
   ```

9. Let's say I want to change the price color to pink. I'll give it a class, remember in `JSX` our class attribute is called `className` not `class`

   ```jsx
   <CookieWrapper>
     <img alt={cookie.name} src={cookie.image} />
     <p>{cookie.name}</p>
     <p className="cookie-price">{cookie.price} KD</p>
   </CookieWrapper>
   ```

10. In `CookieWrapper`, inside the `p` tag I'll add the `cookie-price` class

    ```
    p {
      text-align: center;

      .cookie-price {
        color: #ff85a2
      }
    }
    ```

11. Nothing happened. To apply a class inside a tag we need to add the `&` sign

    ```
    p {
      text-align: center;

      &.cookie-price {
        color: #ff85a2
      }
    }
    ```
