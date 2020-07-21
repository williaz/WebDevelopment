- Most Angular code can be written with just the latest JavaScript, using types for dependency injection, and using decorators for metadata.

https://angular.io/guide/architecture-services
https://stackblitz.com/edit/angular-zmqxns

# Concepts
- an Angular app is defined by a set of NgModules. Angular provides the Routerservice to help you define navigation paths among views. 
  - The basic building blocks are NgModules , which provide a compilation context for **components**. 
  - An app always has at least a **root module** that enables bootstrapping, and typically has many more **feature modules**.
- Components **define view**, which are sets of **screen elements**
- Components **use services**, which provide specific functionality not directly related to views. Service providers can be injected into components as dependencies , making your code modular, reusable, and efficient.
- Modules, components and services are classes that use decorators . 
  - These decorators mark their type and provide metadata that tells Angular how to use them.
  - The metadata for a component class associates it with a **template** that defines a view. A template combines ordinary HTML with Angular directives and binding markup
  - The metadata for a service class provides the information Angular needs to make it available to components through dependency injection (DI) .

## Module
- Organizing your code into distinct functional modules
  - reusability
  - lazy-loading — loading modules **on demand** — to minimize the amount of code that needs to be loaded at startup

- Together, a component and template define an Angular view.
- The dependency injector provides services to a component

- They can contain components, service providers, and other code files whose scope is defined by the containing NgModule. 

- @NgModule()
  - declarations: The components , directives , and pipes that belong to this NgModule.
  - exports: The **subset of declarations** that should be visible and usable in the component templates of **other** NgModules.
    - A root NgModule has no reason to export anything because other modules don't need to import the root NgModule.
  - imports: Other modules whose exported classes are **needed** by component templates declared in this NgModule.
  - providers: Creators of **services** that this NgModule contributes to the global collection of services; they become accessible in all parts of the app. (You can also specify providers at the component level, which is often preferred.)
  - bootstrap: The main application view, called the root component , which hosts all other app views. Only the **root Ng module** should set the bootstrappropert

https://angular.io/guide/architecture-modules
- The components that belong to an NgModule share a compilation context.
- A view hierarchy can mix views defined in components that belong to different NgModules. 
  - a component - a host view
- In JavaScript each file is a module and all objects defined in the **file** belong to that module. 
  - https://exploringjs.com/es6/ch_modules.html
  - Angular loads as a collection of JavaScript modules - library modules. Each Angular library name begins with the @angular prefix. Install them with the node package manager npm and import parts of them with JavaScript import statements.
  - import VS @NgModule imports:






## Component
- Every Angular application has at least one component, the **root component** that connects a component hierarchy with the page document object model (**DOM**). 
- Each component defines a class that contains application data and logic, and is associated with an HTML template that defines a view to be displayed in a target environment.

- [x] [module VS componenet](https://stackoverflow.com/questions/40073941/whats-the-difference-between-an-angular-component-and-module#:~:text=Typically%20module%20is%20a%20cohesive,will%20make%20up%20your%20application.)
- your modules declare which components can be used by components belonging to other modules, which classes will be injected by the dependency injector and which component gets bootstrapped. Modules allow you to manage your components to bring modularity to your app.

- A component controls a patch of screen called a view.

- @Component metadata configures
  - templateUrl: host view: associates a template .html
  - selector: a HTML tag: how the component can be referenced in HTML
  - providers: what services it requires.




### lifecycle TODO
https://angular.io/guide/lifecycle-hooks




### Template
- A template combines HTML with Angular markup
- Your template can use data binding to coordinate the app and DOM data, pipes to transform data before it is displayed, and directives to apply app logic to what gets displayed.
- Template **directives** provide program logic, and binding markup connects your application data and the DOM.
  - types:
    - structural: alter **layout**
      - ```*ngFor *ngIf```
    - attribute: alter the **appearance** or behavior of an existing element.
      - ```ngModel```
    - component
      - ngStyle, ngClass
- 2 types of **data binding**
  - Event binding: responds to user input
    - ```(click)
  - Property binding: interpolate computed value into HTML (component to DOM)
    - interpolcation ```{{hero.name}}```
    - property binding ```[hero]```
  - Two-way data binding
    - template-drive forms
    - ```[(ngModel)]="hero.name"```
  - Angular **processes all data bindings once for each JavaScript event cycle**, from the root of the application component tree through all child components.
  
#### Pipes
- Your templates can use **pipes** to improve the user experience by transforming values for display.
- declare display-value transformations  in template HTML
- A class with the @Pipe decorator defines a function that transforms input values to output values for display in a view.








## Services and dependency injection
- For data or logic that isn't associated with a specific view, and that you want to **share across components**, you create a service class.
- Dependency injection (DI) lets you keep your component classes lean and efficient. They don't fetch data from the server, validate user input, or log directly to the console; they **delegate such tasks to services**


### VS component
- Component is view Controller: Ideally, a component's job is to enable the user experience and nothing more. A component should present properties and methods for data binding, in order to mediate between the view (rendered by the template) and the application logic (which often includes some notion of a model).
- Reusable Service: A component can delegate certain tasks to services, such as fetching data from the server, validating user input, or logging directly to the console. By defining such processing tasks in an injectable service class, you make those tasks available to any component. 

#### Injecter = container; provider: bean method; looking at the constructor parameter types for dependency
- For any dependency that you need in your app, you must register a provider with the app's injector, so that the injector can use the provider to create new instances. For a service, the provider is typically the service class itself.


#### scope
- root
- NgModule
- component


https://angular.io/guide/dependency-injection


### Rounting
- The Angular RouterNgModule provides a service that lets you **define a navigation path** among the different application states and view hierarchies in your app. 

- The router maps URL-like paths to views instead of pages.
  - When a user performs an action, such as clicking a link, that would load a new page in the browser, the router **intercepts the browser's behavior, and shows or hides view hierarchies**.
  - The router **logs activity** in the browser's history, so the **back and forward buttons** work as well.






# Dev workflow
https://angular.io/guide/build
# Configuration
https://angular.io/guide/file-structure

- workspace contains 1 or more projects
- ng new <my-prejct>: a new worksapce with a same name project







# Coding style
https://angular.io/guide/styleguide

