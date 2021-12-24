### Chapter 6
### Building with CLI
#### step by step using vue-cli


-----------------------------------------------------------------------------------------

### 6.1. Instaling Project with cli

* we'll start to use Vue CLI, CLI stands for a Command Line Interface. 
* steps 
     * instal nodejs => [https://nodejs.org/en/]
     * install vue global =>  npm install -g @vue/cli          
     * create project =>  vue create project-name
     * there's many opetions will appear 
       * we'll select manually select features 
    * then we should choose manually selected features are,
        * (*) which mean selected (you can select or un select using space)
        * we will just install some & install part of them later 
        * we will not install any thing just that selected by default 
    * version 
       * here we will 2
    * Pick a linter / formatter config
       * ESLint + Prettier
    * Pick additional lint features: 
        * Lint on save
    * Where do you prefer placing config for Babel, ESLint, etc.?
     *  In package.json    
    * Save this as a preset for future projects? 
     * N 
     * You can this preset with specific name & use it for future project 
    * after install project 
      * go to project
      * run => npm run serve 
      *  App running at:
             * Local:   http://localhost:8080/
             * Network: 
     * go to browser & fo to local url  [http://localhost:8080/]


---------------------------------------------------------------------------------------------------------------------
### 6.2 Understanding Vue CLI installation
   
   * Read.md file 
       *  has all the different commands that you can run. 
    
   * package.json 
      * has different options for the project. 
         * ```  "scripts": {
                    "serve": "vue-cli-service serve",
                    "build": "vue-cli-service build",
                    "lint": "vue-cli-service lint"
                 } ```
         * here our commands serve actual run ` vue-cli-service serve `
         * you will find modules/libraries/plugins/packages that's been installed .
         *  In addition to that you'll see some places where you can configure your options a bit further.
           * Ex `eslintConfig`
   * package-lock.json
      * Which is a more detailed version of the package . 
   * babel.config.js 
     * converting any sort of code that you write . So, that its more compatible with older versions of your browsers.
   * .gitignore
        *    just shows you the things that are not going to be uploaded to git .
   * (src) source folder 
        * which is the most important folder. 
        * components folder
         * the place where we will add our components
        *   app.js 
         *  file is where our main components are going to sit.
        * assets folder
         *  where we will put any images
    *  public folder
       * favicon which is the icon that loads up in your tabs right here on a browser 
       * index.html 
        * There is one tag where your application is going to load and its this tag right here. 
       * This is for things that you don't really need to do anything in vue JS with so you could put additional images .
         So you could sort of put any HTML code that is not going to be controlled by vue JS in here. But everything else can be your own code. So if you were building this as part of some other web page, you would just put in any scripts you want in here as well as any CSS. There's also a . And you would just put anything else you want in the public folders. 
       
       

------------------------------------------------------------------------------------------------------------------------------------
### 6.3. How CLI components load

* in the public folder we  have index.html file, and the most important thing you need to know is that the application is all going to be loaded in this div that has the id of app. `   <div id="app"></div> `
*  in the source folder, we have main.js file, and this is actually looking for that element with an id of app and mounting the application. ``` new Vue({ render: (h) => h(App), }).$mount("#app"); ```
* app.vue file will be mounted into our element with the id of App
* app.vue 
  * file look like split into 3 parts 
    * template 
     * the same thing as when we create a component and we give that component a template attribute.
     * don't forget that our template must have only one root element . so here if we create new separate div for example will not work 
     * in app.vue file we'll find  something called HelloWorld. which is a subcomponent and it's passing along a prop with some text.
    * script
     * The script section is where we would put the JavaScript, so this will be the equivalent of a script tag in a regular index that html file.
     * in app.vue we import HelloWorld component from another file . 
     *  then we will find export to export this component with the name of app. And it's also notifying Vue.js that this is using a component called HelloWorld.  ``` export default { name: "App", components: {  HelloWorld,},}; ``` 
    * style 
     *  This is where you would put any styles that you want to apply to this specific component.
* HelloWorld.vue 
  *  we have the same structure
  *  style have something called scope. 
   * scoped means that this style is going to apply to this component only.
* but in the App.vue file cause of style not scoped style will apply to all subcomponents. 


-------------------------------------------------------------------------------------------------------------------------------------
### 6.4.  Installing additional modules
 * we'll install what'll need in our project 
  * go to your project 
  *  npm i --save animate.css@3.7.0 bootstrap@4.2.1 jquery@3.3.1  popper.js vue-router
  * npm i --save @fortawesome/fontawesome-free @fortawesome/fontawesome-svg-core @fortawesome/vue-fontawesome @fortawesome/free-solid-svg-icons
  * we will made some edits in main.js 
    ` import "bootstrap"; ` 
    ` import "bootstrap/dist/css/bootstrap.css"; `
    ` import "animate.css/animate.css"; ` 
 * also , import icons that we'll use it 
   ``` import {library} from '@fortawesome/fontawesome-svg-core';
    import {
        faShoppingCart,
        faDollarSign
      } from "@fortawesome/free-solid-svg-icons";

library.add(faShoppingCart, faDollarSign); ``` 

--------------------------------------------------------------------------------------------------------------------------
### 6.5. Testing your module installations
 * we just check it 
   * using class container to check if bootstrap work or not in app.vue ` <div id="app1" class="container">`
   * also , using fontawesome icon the way we use font-aweasom this blog is useful (https://blog.fontawesome.com/how-to-use-vue-js-with-font-awesome/)
   * we know the name of icon form fontawesome website 
   *   ` <font-awesome-icon icon="shopping-cart"></font-awesome-icon> ` in our example i use shopping-cart 
   * also we should import vue-fontawesome ` import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome';` & register as subcomponent `components: {FontAwesomeIcon}`

-----------------------------------------------------------------------------------------------------------------------------
### Chapter6 End 
