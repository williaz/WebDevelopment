- Most Angular code can be written with just the latest JavaScript, using types for dependency injection, and using decorators for metadata.


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
  - imports: Other modules whose exported classes are **needed** by component templates declared in this NgModule.
  - providers: Creators of **services** that this NgModule contributes to the global collection of services; they become accessible in all parts of the app. (You can also specify providers at the component level, which is often preferred.)
  - bootstrap: The main application view, called the root component , which hosts all other app views. Only the **root Ng module** should set the bootstrappropert

https://angular.io/guide/architecture-modules

## Component
- Every Angular application has at least one component, the **root component** that connects a component hierarchy with the page document object model (**DOM**). 
- Each component defines a class that contains application data and logic, and is associated with an HTML template that defines a view to be displayed in a target environment.

module VS componenet

### Template
- A template combines HTML with Angular markup
- Template directives provide program logic, and binding markup connects your application data and the DOM.
- 2 types of **data binding**
  - Event binding: responds to user input
  - Property binding: interpolate computed value into HTML
- Angular supports two-way data binding , meaning that changes in the DOM, such as user choices, are also reflected in your program data.
- Your templates can use **pipes** to improve the user experience by transforming values for display.

## Services and dependency injection
- For data or logic that isn't associated with a specific view, and that you want to **share across components**, you create a service class.
- Dependency injection (DI) lets you keep your component classes lean and efficient. They don't fetch data from the server, validate user input, or log directly to the console; they **delegate such tasks to services**

### Rounting
- The Angular RouterNgModule provides a service that lets you **define a navigation path** among the different application states and view hierarchies in your app. 

- The router maps URL-like paths to views instead of pages.
  - When a user performs an action, such as clicking a link, that would load a new page in the browser, the router **intercepts the browser's behavior, and shows or hides view hierarchies**.
  - The router **logs activity** in the browser's history, so the **back and forward buttons** work as well.






# Dev workflow
https://angular.io/guide/build
# Configuration
https://angular.io/guide/file-structure
# Coding style
https://angular.io/guide/styleguide

