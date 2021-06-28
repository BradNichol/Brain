# Decorators

## @Input()
Mark a class property as an input property, which can bind it to a supplied DOM property from another component.

```aidl

<app-hero-detail [hero]="selectedHero"></app-hero-detail>

```
Here, the selectedHero property from a parent component is bound to the [hero] property of the app-hero-details component. 
Actions in the parent component are passed down.

## @Injectable()
Marks a class as available for dependency injection. Service classes typically use it.
Once a class is marked as @Injectable, it can be injected into other classes via the constructor.
```aidl

constructor(private heroService: HeroService) {}

```
