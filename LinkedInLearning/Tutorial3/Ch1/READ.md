### Chapter1
#### in this chapter we will just install vue cli , create new prject & install some modules , info in this chapter is repeated

--------------------------------------------
### 1.1. Installing Vue CLI
* in this tutorial we will start using vue cli directly.
 * install steps 
    * instal nodejs => [https://nodejs.org/en/]
    * install vue global => npm install -g @vue/cli  
    * create project => vue create project-name
     * there's many opetions will appear
        * we'll select manually select features
           * then we should choose manually selected features are, -- you can what you want --  
           * (*) which mean selected (you can select or un select using space)
           * we will just install some & install part of them later
           * we will not install any thing just that selected by default
           * version
            * here we will use 2
           * Pick a linter / formatter config
             * ESLint + Prettier
           * Pick additional lint features:
            * Lint on save
           * Where do you prefer placing config for Babel, ESLint, etc.?
             * In package.json
           * Save this as a preset for future projects?
             * N -- 
             * you can type Y => which means we need to save this preset (our settings for future projects & named it -- 
            * after install proje
              * go to project
              * run => npm run serve
              * App running at: * Local: http://localhost:8080/ * Network:
              * go to browser & fo to local url [http://localhost:8080/]


-------------------------------------------------------------------------------------------------------------------------------------
### 1.2. Understanding Vue CLI installation
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
           * Example  `eslintConfig`
   * package-lock.json
      * Which is a more detailed version of the package . 
   * babel.config.js 
     * converting any sort of code that you write . So, that its more compatible with older versions of your browsers.
   * .gitignore
        *    just shows you the things that are not going to be tracked by git .
   * (src) source folder 
        * which is the most important folder. 
        * components folder
         * the place where we will add our components
        *   app.vue
         *  file is where our main components are going to sit.
        * assets folder
         *  where we will put any images
    *  public folder
       * favicon which is the icon that loads up in your tabs right here on a browser 
       * index.html 
        * There is one tag where your application is going to load and its this tag right here. 
       * This is for things that you don't really need to do anything in vue JS with so you could put additional images .
         So you could sort of put any HTML code that is not going to be controlled by vue JS in here. But everything else can be your own code. So if you were building this as part of some other web page, you would just put in any scripts you want in here as well as any CSS. There's also a . And you would just put anything else you want in the public folders. 
       * we  have index.html file, and the most important thing you need to know is that the application is all going to be loaded in this div that has the id of app. `   <div id="app"></div> `
       
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

### 1.3. Installing custom modules
* in this lesson we will install some modules 
  *  npm i --save bootstrap@4.3.1 popper.js jquery
  * npm i --save npm i --save axios moment lodash
  * npm i --save @fortawesome/fontawesome-free @fortawesome/fontawesome-svg-core @fortawesome/free-solid-svg-icons @fortawesome/vue-fontawesome
   * notes :
      *  i == install 
      * we'll use here axios instead of fetch that we used in tutorial 2
      * lodash => common libary for dealing with arrays and objects
      * moment => common library dealing with dates (for parsing, validating, manipulating, and formatting dates)


------------------------------------------------------------------------------------------------------------------------------
    
