1. Let's open our application and take a look at its structure and explore the main files:

   1. `package.json`: Every `yarn` project must have this file. It basically gives `yarn` all the information it needs to know about the app and the used dependencies.
   2. `README.md`: A file with some information about the application. It's okay to remove it.
   3. `.gitignore`: A file that contains the name of files and directories that github should ignore and not push to the repository.
   4. `node_modules`: A folder that contains all the libraries and dependencies that `yarn` downloaded.
   5. `public`: A folder that has the images, fonts and an html file which is the main file in our application.
   6. `src`: The main folder that we will interact with when building our application. For now, we care about two files in it:
      1. `App.js`: This is where we will write our code.
      2. `index.js`: Connects `App.js` to `index.html` which renders the code on the screen.

2. Now let's go to `App.js` where all the magic happens, and see what's going on. In the first line there is the following line of code which basically tells the JS file that this file is using React. You cannot use React without it.

   ```javascript
   import React from "react";
   ```

3. We are also importing the logo and a css file. Let's not worry about them now.

4. Then we can see a function named `App`, and inside this function's return value there is some code that looks just like HTML. Well, guess what? IT'S NOT HTML!! This is JSX.

5. Finally at the end of the file there is `export default App` which is how we export stuff in JavaScript.

6. Now let's try editing some of the text in our website. I'll add a `Hello World!` under the logo.

   ```jsx
   <img src={logo} className="App-logo" alt="logo" />
   <h3>HELLOO WORLD!</h3>
   ```

   So it actually works like HTML, but what makes JSX different than HTML?

7. The first difference is already clear, the class attribute in HTML is called `class` while in JSX it's called `className`.

8. Let's remove all the JSX code, the logo and CSS imports and start building our website's home page and learn the differences.

   ```jsx
   function App() {
     return (

     );
   }

   export default App;
   ```
