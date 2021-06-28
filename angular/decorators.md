# Decorators

## @Input()
Mark a class property as an input property, which can bind it to a supplied DOM property from another component.

```aidl

<app-hero-detail [hero]="selectedHero"></app-hero-detail>

```
Here, the selectedHero property from a parent component is bound to the [hero] property of the app-hero-details component. 
Actions in the parent component are passed down.

