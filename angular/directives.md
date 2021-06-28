# Angular Directives

### *ngFor
Used to loop around objects to display data. *ngFor is a repeater directive.
```aidl

<li *ngFor="let data of object">

```

### *ngIf
*ngIf is a structural directive that is used to conditionally display information if a certain condition is true. If true, the data is
pushed into the DOM or removed from the DOM if the condition is false.
```aidl

<div *ngIf="dataAvailable">
    // show content contained between div elements.

```