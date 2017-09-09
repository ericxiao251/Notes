# How to setup a node project

1. Initialize your node project.
* run `npm init` in your project directory.
* This will create a `package.json` file that will contain all your **dependencies** and **scripts**.

2. Install your dependencies.
* we will have 2 types of dependencies **production** and **dev** dependencies.
* run `npm i -S ...` to install all your dependencies.
* run `npm i -D ...` to install all your dependencies for development.
* run `npm i -S ...@version_number` to install a specific version of a package.

3. Libraries:

    Main backend dependencies:
      * `express`:
        * to create a node web server.
      * `mongodb`:
        * to connect to Mongo from Node.

    Main frontend dependencies:
      * `react`:
        * use React library to describe our user interfaces.
      * `reactdom`:
        * use ReactDOM library to render those user interfaces on both the frontend and the backend.

    Tools:
      * `webpack`:
        * used to translate modular code into something that browsers understand.
      * `babel`:
        * transform the JSX extension code into what React understands. As well transform a few of the modern JS features that are not yet supported natively in all browsers.
      * `nodemon`:
        * when we make changes to our node project, a reset is required. With nodemon, it will monitor our files and auto-restart Node for us when we save changes to disk.
      * `eslint`:
        * self explained.

4. setup startup scripts
* Look at the `scripts` keyword in the `package.json`.
  * want to use `nodemon` and `babel-node` to run our project.
  * want to bundle all our javascript files using `webpack`.
