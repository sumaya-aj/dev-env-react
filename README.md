# Development Environment - React JS
 
- based on https://jscomplete.com/learn/1rd-reactful

[1] install dependencies__
[2] configure dependencies__
[3] run server and webpack__


-------------------------
[1] install dependencies
-------------------------
1. run: ``` cd needDir ```
2. run: ``` npm init -y ```
    * creates package.json
3. run: ``` npm i express ``` 
    * npm will place the installed express package under node_module folder that it creates
    * npm will write the new dependency (express) in package.json
4. run ``` npm i react react-dom ```
    * react: core library
    * react-dom: used to render react app to the dom or when we use server-side rendering. (DOM is a a renderer. SSR is a renderer)
5. run ``` npm i webpack webpack-cli ```
    * webpack is a module bundler. Used to ship the modules we write to the browser as a single bundle, because browsers don't understand modules yet
6. run ``` npm i babel-loader @babel/core @babel/node @babel/preset-env @babel/preset-react ```
    * babel is the package that compiles jsx into regular react api calls
    * babel loader is a package that hooks babel into the webpack process, to tell webpack that while it's bundling the system, if it sees any jsx, it shall invoke babel to convert jsx into react api calls
    * babel/core: babel compiler
    * babel/node: needed if you're doing SSR, and to understand jsx
    * the two presets: are the minimum configuration to tell babel to compile react
    * env preset: if you want to use any modern js and you want to target older browsers
    * react preset: for jsx  
7. run ``` npm i -D nodemon ```
    * nodemon is a package that restarts node automatically when we change things in node and save it to the disk 
    * nodemon is a watcher on top of node command
8. run ``` npm i -D eslint @babel/eslint-parser eslint-plugin-react eslint-plugin-react-hooks ```
    * ESLint immediately analyze your code and tell you if you have a problem or your code is lacking certain qualities
    * babel-eslint: eslint that understands babel
    * eslint-plugin-react: eslint that understand jsx and recommended settings specific for react


---------------------------
[2] configure dependencies
---------------------------    

1. configure ESLint
    * add file in the root of the project called ``` .eslintrc.js ```
    * paste in the object (refer to the article)
2. configure babel 
    * add file in the root of the project called ``` babel.config.js ```
    * paste in the object (refer to the article) 
3. configure webpack
    * file structure is related to webpack configuration
    * add file in the root of the project called ``` webpack.config.js ```
    * paste in the object (refer to the article)


---------------------------
[3] run server and webpack
---------------------------

* to run webpack and server:
  in package.json > scripts
    1. run server: add ``` "dev:server": "nodemon --exec babel-node src/server/server.js --ignore dist/" ```
    2. create the bundle using webpack command: add ```  "dev:bundler": "webpack -w --mode=development" ``` 
      * -wd : w for watch, d for development
      
    
* file structure:
  1. run  ``` mkdir dist ```
  2. run  ``` mkdir src ```
  3. run  ``` cd src ```
  4. run  ``` mkdir components ```
  5. run  ``` mkdir server ```


* from article:
  1. add src/server/server.js
  2. add sample react component in src/components/App.js
  3. add src/index.js (DOM renderer) 


* run the app:
  1. ``` npm run dev:server ```
  2. ``` npm run dev:bundler ```
    
