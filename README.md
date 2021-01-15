# Angular Workshop

## Learning objectives

## The Mission

## Initiate your Project

- Make sure you have Node.js and NPM installed (`npm install -g npm@latest`)

- Install the Angular CLI : `npm install -g @angular/cli`

- Create your project : `ng new my-cool-project-name --style=scss --skip-tests=true`

(Here you directly configurate it to use SCSS and specify to skip the test '.spec' files that we won't use for this workshop)

- Go to your project `cd my-cool-project-name` and install Bootstrap : `npm install bootstrap@3.3.7 --save`.
  Then in your project, in the file `angular.json`, modify the styles array to have :
  
  `"styles": [
              "node_modules/bootstrap/dist/css/bootstrap.css",
              "src/styles.scss"
            ], `
            
- You can now launch the server in your terminal : `ng serve --open`
You should see, the Angular Welcome Page opened in your browser.

Congrats, you are good to go ! \o/

## Built your App

- Delete everything in app.component.html

### Make your first Component :

1. In this component we are gonna display the list of all our famous people, in the terminal type :
 `ng generate component famous-people-list`
 (or  : `ng g cfamous-people-list`)
 
 You now have a folder with a template, a style and ts files for this component!
 
 2. Now go back to app.component.html and modify it to have : 
 ```
 <div class="container">
  <div class="row">
    <div class="col-xs-12">
      <app-famous-people-list></app-famous-people-list>
    </div>
  </div>
</div>
 ```
 
 
 
 


## Time to showboat ! Here is how you can display your App on Github :

## Tips
