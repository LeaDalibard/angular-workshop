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

1. We are gonna make a Famous People List component, where we are gonna display the list of all our famous people.
In the terminal type :
 `ng generate component famous-people-list`
 (or  : `ng g c famous-people-list`)
 
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
 Have a look at your browser, you can see the template of your component!
 
3. In **famous-people-list.component.ts** : Add a variable famousPeople which is an array of objects (we will make it dynamic later)

```
famousPeople = [
    {
      fName: 'First Name 1',
      lName: 'Last Name 1',
      description: 'Description 1',
      advantages: 0,
      disadvantages: 0,
    },
    {
      fName: 'First Name 2',
      lName: 'Last Name 2',
      description: 'Description 2',
      advantages: 0,
      disadvantages: 0,
    },
    {
      fName: 'First Name 3',
      lName: 'Last Name 3',
      description: 'Description 3',
      advantages: 0,
      disadvantages: 0,
    }
  ];
```
4.  In **famous-people-list.component.html** :

Displays your arrays famous people in a list-group (Remember you have Bootstrap installed), and for each item display the First Name, Last Name and Description and add 2 buttons "Pros" and "Cons".

**Tips** :

- Use [interpolation] (https://angular.io/guide/interpolation) to communicate from code to template
- Use [*ngFor](https://guide-angular.wishtack.io/angular/composants/ngfor) to loop inside your array


You should have something like that : 

5. Add 2 methods `onClickAddPros()` and `onClickCons()` to make the button dynamic so that when you click on Pros, you increase advantage counter and on Cons disadvantages counter.

**Tips** :
- Use [Event binding] (https://angular.io/guide/event-binding) 



## Time to showboat ! Here is how you can display your App on Github :


