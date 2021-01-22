# Angular Workshop

## Learning objectives

## The Mission

<img src="/ross-laminated-list.jpg" alt ="ross-laminated-list" width="400" />

Make a very useful Application to make you own list of famous people you would like to date !

## Initiate your Project

- Make sure you have Node.js and NPM installed (`npm install -g npm@latest`)

- Install the Angular CLI : `npm install -g @angular/cli`

- Create your project : `ng new my-cool-project-name --style=css --skip-tests=true`

(Here you directly configurate it to use CSS and specify to skip the test '.spec' files that we won't use for this workshop)

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
 
3. Make a [service](https://angular.io/tutorial/toh-pt4) : 


`ng generate service famousPeople`

In this file we are gonna deal with our data : add a Famous People, modify or delete one...


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

4. In **famous-people-list.component.ts** : 

Import the FamousPeopleService.
Add a private FamousPeopleService parameter of type FamousPeopleService to the constructor.

Declare a variable `famousPeople=[] ;`

And instance it inside [ngOnInit](https://angular.io/api/core/OnInit)  to be :

```
ngOnInit(): void {
    this.famousPeople = this.famousPeopleService.famousPeople;
  }
```
This way you can access the data from your  FamousPeopleService.

5.  In **famous-people-list.component.html** :

Displays your arrays famous people in a list-group (Remember you have Bootstrap installed), and for each item display the First Name, Last Name and Description and add 2 buttons "Pros" and "Cons" displaying the numbers of advantages and disadvantages.

**Tips** :

- Use [interpolation] (https://angular.io/guide/interpolation) to communicate from code to template
- Use [*ngFor](https://guide-angular.wishtack.io/angular/composants/ngfor) to loop inside your array


You should have something like that : 

![pros,cons](/pros-cons.png)

6. Let's add counter to our buttons using [Event binding] (https://angular.io/guide/event-binding) !

 In **famous-people-list.component.html** :
 Add **index** to your `*ngFor` and add a method to your button Pros using this index as a parameter : `(click)="onClickAddPros(i)"`
 
 In **famous-people-list.component.ts** :
 Add a method `onClickAddPros()` :
 ```
 onClickAddPros(i: number) {
    this.famousPeopleService.addPros(i);
  }
  ```
Remember ? We are managing our data in famousPeopleService, so in  **famousPeople.service.ts**, add the method addPros that actually increases our advantage counter when clicking the buttons :

```
 addPros(i: number) {
    this.famousPeople[i].advantages++;
  }
```
Do the same for the disadvantages counter.

**Extra** :
- Use [ngClass](https://www.angularjswiki.com/angular/how-to-add-a-class-based-on-condition-in-angular/) to change background color depending on Pros and Cons.


### Make a form where you can add your famous people :

1. Create a new Component AddPeopleComponent.
2. In the template, create a form with inputs First name, Last Name and Description.
3. Add attributes "name" and [ngModel](https://angular.io/api/forms/NgModel) to inputs to signal Angular which inputs to check.

As an example for First name you should have something like :

```
<div class="form-group">
        <label for="fname">
          First name :
        </label>
        <input type="text" id="fname" class="form-control"  name="fname" ngModel >
      </div>
```

4. To submit the form add the following to your template :

` <form (ngSubmit)="onSubmit(myForm)" #myForm="ngForm"> `

`<button class="btn btn-primary" type="submit">Add</button>`

5. In **add-people.component.ts**, import famousPeopleService, and passed it as an argument in your constructor.

Add the `onSubmit()` method which take value from the form and use a addFamousPeople method from Services to pass it to your form FamousPeople (as we did for the advantages and disadvantages counters).
You can now replace your initial famousPeople Array by an empty one, as you will be filling it yourself.

7. Congrats you are done with the requirements, go add styling and extra useful functionnality to you app !


### Nice to Have:

- Add validation to your form
- Add a delete button **Tips** : Use splice()
- Make a model for Famous people
- Use Routing
- Add other functionnalities : photos, comment, sort by, changed color depending of pros and counters
- Add some styling
- Add edit function
- Save your datas using XXXXX


## Time to showboat ! Here is how you can display your App on Github :

- ng build --prod`
- `ng add angular-cli-ghpages`
- `ng deploy --base-href=/<repositoryname>/`

Your project should be available at https://<username>.github.io/<repositoryname>
  
  ![Alt Text](https://media.giphy.com/media/uYWDhmIl11XI4/giphy.gif)





