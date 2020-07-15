1. Let's move to `CookieList`, I want you all to tell me what the styled component will look like, let's call it `ListWrapper` and copy the styling from `styles.list`.

```javascript
const ListWrapper = styled.div`
  align-items: center;
  justify-content: center;
  display: flex;
`;
```

2. Don't forget to export it

```javascript
export { Description, ListWrapper, Title, ShopImage };
```

3. In `CookieList`, import `ListWrapper` and replace `div` with it

```javascript
// Styling
import { ListWrapper } from "../styles";
```

4. Replace `div` with `ListWrapper`

```javascript
return <ListWrapper>{cookieList}</ListWrapper>;
```

5. In `CookieItem`, I'm gonna go for a different approach with styled components. Since we said that styled components uses CSS, let's apply some of the CSS properties we learnt.

6. Let's start with creating a styled component called `CookieWrapper` for the `div` in `CookieItem`, move the style from `styles.cookie` and convert it to CSS.

```javascript
const CookieWrapper = styled.div`
  margin: 20px;
`;
```

7. Don't forget to export and import `CookieWrapper`.

```javascript
export { CookieWrapper, Description, ListWrapper, Title, ShopImage };
```

8. Apply the changes in `CookieItem`. Also let's remove the styling coming from `styles`

```jsx
<CookieWrapper>
  <img alt={cookie.name} src={cookie.image} />
  <p>{cookie.name}</p>
  <p>{cookie.price} KD</p>
</CookieWrapper>
```

9. Now `img` and `p` are inside `div`, we don't need to create a styled component for each of them. We can apply a certain style for all `img` and `p` tags inside `CookieWrapper`. Let's start with `img` tag:

```javascript
const CookieWrapper = styled.div`
  margin: 20px;

  img {
    width: 200px;
    height: 200px;
  }
`;
```

10. How cool is that? Let's style the `p` tag:

```javascript
const CookieWrapper = styled.div`
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

11. Let's say I want to change the price color to pink. I'll give it a class, remember in `JSX` our class attribute is called `className` not `class`

```jsx
<CookieWrapper>
  <img alt={cookie.name} src={cookie.image} />
  <p>{cookie.name}</p>
  <p className="cookie-price">{cookie.price} KD</p>
</CookieWrapper>
```

12. In `CookieWrapper`, inside the `p` tag I'll add the `cookie-price` class

```css
p {
text-align: center;

  .cookie-price {
    color: #ff85a2
  }
}
`;
```

13. Nothing happened. To apply a class inside a tag we need to add the `&` sign

```css
p {
text-align: center;

  &.cookie-price {
    color: #ff85a2
  }
}
`;
```
