# Angular Workshop

## Learning objectives

## The Mission

## Initiate your Project

- Make sure you have Node.js and NPM installed (`npm install -g npm@latest`)

- Install the Angular CLI : `npm install -g @angular/cli`

- Create your project : `ng new my-cool-project-name --style=scss --skip-tests=true`

(Here you directly configurate it to use SCSS and specify to skip the test '.spec' files that we won't use for this workshop)

- Go to your project `cd my-cool-project-name` and install Bootstrap : `npm install bootstrap --save`.
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

1. We are gonna make a FamousPeopleListComponent, where we are gonna display the list of all our famous people.
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
 
4. Now make a directory **services** and inside a file **famousPeople.service.ts**

=>In App module Services have to be imported and put in providersArray

In **famousPeople.service.ts** : Add a variable famousPeople which is an array of objects (we will make it dynamic later)

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

In **famous-people-list.component.ts** : Import service in constructor and call your posts onInit

4.  In **famous-people-list.component.html** :

Displays your arrays famous people in a list-group (Remember you have Bootstrap installed), and for each item display the First Name, Last Name and Description and add 2 buttons "Pros" and "Cons".

**Tips** :

- Use [interpolation] (https://angular.io/guide/interpolation) to communicate from code to template
- Use [*ngFor](https://guide-angular.wishtack.io/angular/composants/ngfor) to loop inside your array


You should have something like that : 

![pros,cons](/pros-cons.png)

5. Add 2 methods `onClickAddPros()` and `onClickAddCons()` to make the button dynamic so that when you click on Pros, you increase advantage counter and on Cons disadvantages counter . They should call 2 methods in **famousPeople.service.ts** :`addPros()` and `addCons()`.

**Tips** :
- Use [Event binding] (https://angular.io/guide/event-binding) 
- Add **index** to your `*ngFor` and pass it as an argument to your methods

### Make a form where you can add your famous people :

1. Create a new Component AddPeopleComponent.
2. In the template, create a form with inputs First name, Last Name and Description.
3. Add attributes "name" and ngModel to inputs to signal Angular which inputs to check.

As an example for First name you should have something like :

```
<div class="form-group">
        <label for="fname">
          First name :
        </label>
        <input type="text" id="fname" class="form-control"  name="fname" ngModel required>
      </div>
```
4. To submit the form add the following to your template :
` <form (ngSubmit)="onSubmit(myForm)" #myForm="ngForm"> `

`<button class="btn btn-primary" type="submit">Add</button>`

5. In **add-people.component.ts**, import famousPeopleService, and passed it as an argument in your constructor.
Add the `onSubmit()` method which take value from the form and use a addFamousPeople method from Services to pass it to your form FamousPeople.
You can now replace your initial famousPeople Array by an empty one, as you will be filling it yourself.

6. Add a delete button in **famous-people-list.component.ts** and onClick call a method `deleteFamousPeople`in famousPeopleService.

**Tips** : Use splice()

7. Congrats you are done with the requirements, go add styling and extra useful functionnality to you app !


### Nice to Have:

-Add validation to your form
-Make a model for Famous people
-Use Routing
-Add other functionnalities : photos, comment, sort by, changed color depending of pros and counters
-Add some styling
-Save your datas using XXXXX


## Time to showboat ! Here is how you can display your App on Github :


