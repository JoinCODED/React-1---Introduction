I believe it's time to move our styled components to the `styles` file.

1. Move all the styled components and the `styled` import to `styles.js`.

2. But now how can we export all those components? `export default` allows us to export one thing only.

3. To export more than one thing we will use the `export {}` command and pass it everything we want to export. Place it at the end of your file:

```javascript
export { Description, Title, ShopImage };
```

4. The way we import them in `App.js` will change also. Basically those components are exported in one object, so we are destructuring our imported object to access the components directly:

```javascript
import { Description, ShopImage, Title } from "./styles";
```