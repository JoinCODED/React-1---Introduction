1. We will use `yarn` to create our React app, manage all the dependencies and run our application.

2. To create a React application, we will run the following command from `yarn`. We will be creating a cookie shop website, so I'll call my app `cookieshop`. Keep in mind that capital letters are not allowed in the app name.

   ```shell
   $ yarn create react-app cookieshop
   ```

3. Viola! Our app is created. But how can we run it?

4. The terminal is giving us some instructions to run our application. All we need to do is go inside the application folder and run `yarn start`!

   ```shell
   $ cd cookieshop
   $ yarn start
   ```

5. Note that the browser opened automatically for us! Take a look at the browser's URL: `localhost:3000`. To see what our code looks like we need to host it on a server, and since we're still in development we don't anyone to have access to the website yet.

6. `yarn start` runs the application on the local host which is my laptop. So in this case my device (my laptop) will act as my host and will run the application.

7. `3000` is the port number, which is a certain location in the host. Think of it this way, if the host is the area in an address, the port is the house number.