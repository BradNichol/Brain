# Angular Overview

## Components
When you first serve the application in your browser, you're seeing the application shell.
The overall application shell is controlled by an Angular component called **AppComponent**.


Components are the building blocks of an Angular application and three files typically make up a
component:

    1. app.component.ts— the component class code, written in TypeScript.
    2. app.component.html— the component template, written in HTML.
    3. app.component.css— the component's private CSS styles.

The .ts file will always contain Component import from the angular/core library, and the @Component
annotation is used to annote the class. This component specifies the metadata.
The metadata properties are:

    1. selector— the component's CSS element selector
    2. templateUrl— the location of the component's template file.
    3. styleUrls— the location of the component's private CSS styles.

ngOnInit() is a lifecycle hook, which immediate calls after launching a component. Any initialization 
logic should go inside the brackets.

To use your component in other place, you must **export** the class, so that it can be imported into
other components. In most cases you'll expose your component inside of AppComponent.

## Pipes
You can format data inside bindings by using the pipe | operator. Pipes can be used to format
strings, numbers, dates etc. Angular comes with several built-in pipes, and you can also create
your own custom ones.

## Data Binding
Angular provides one and two-way binding, to allow data to flow between target elements in a 
component.
**[(ngModel)]** is Angular's two-way data binding syntax.

## External Modules
To add external modules/dependencies to your project, they'll need to be imported inside the top
level AppModule class, which is typically found in app.module.ts.
Import the required module at the top of class, and then add the module to the @NgModule metadata imports
array.

## Declaring a component
Inside the same app.module.ts class, you'll see the declarations array. This is where components that 
you create are declared. If you use the CLI to create a component, it will automatically update 
this array with your new component. otherwise, you can manually 


## Event Binding
Various event binders can be added to html elements to listen for and respond to user actions such as clicks or mouse movements.
One common binder is (click) that can be used to trigger functions when an element is clicked.

## Class Binding
Class binding can be used to toggle a CSS style on an elements class attribute.
```aidl
<li *ngFor="let hero of heroes" (click)="onSelect(hero)" [class.selected]="hero === selectedHero">
```

## Directives
Directives extend functionality to your HTML that can change the style or behaviour of DOM elements.
Angular has three directive types:

    1. Attribute directives
    2. Structural directives
    3. Built-in directives

## Decorators
Decorators are a feature of Typescript and used throughout Angular. Decorators are can customise a class at runtime.
There are various types that can be applied to properties, classes and methods.
For example, @Input() and @Output() decorators can be used to share data between components.











