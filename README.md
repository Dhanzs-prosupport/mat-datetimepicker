# Material Datetimepicker for @angular/material 7.x

This is the main branch for @angular/material 7.x.

### Description

The datetimepicker is taken from [Promact/md2](https://github.com/Promact/md2), modified to use @angular/material as base and added theming support and forked from [kuhnroyal/mat-datetimepicker](https://github.com/kuhnroyal/mat-datetimepicker#readme) to support angular 7.x.

### Installation
Install:
```
yarn install @angular/material-datetimepicker/core
```
And for the moment adapter:
```
yarn install @angular/material-moment-adapter
yarn install @prosupport//material-datetimepicker-moment
``` 

### Performing a local build
```
yarn install
yarn build
``` 

### Using the local build in some project
```
cd my-project
``` 
Add the dependencies to your `package.json`:
```
"dependencies": {
    "@prosupport/material-datetimepicker-core": "x.x.x",
    "@prosupport/material-datetimepicker-moment": "x.x.x",
}
```
Link the local built modules:
```
yarn link "@prosupport/material-datetimepicker-core"
yarn link "@prosupport/material-datetimepicker-moment"
``` 

### Import  & configuration
Basically the same way the @angular/material datepicker is configured and imported.

```
imports: [
  ...
  MatDatepickerModule,
  // use this if you want to use native javascript dates and INTL API if available
  // MatNativeDatetimeModule,
  MatMomentDatetimeModule,
  MatDatetimepickerModule
]
```

@see [src/app/app.module.ts](src/app/app.module.ts)

### Usage
```
<form [formGroup]="group">
  <mat-form-field>
    <mat-placeholder>Start DateTime</mat-placeholder>
    <mat-datetimepicker-toggle [for]="datetimePicker" matSuffix></mat-datetimepicker-toggle>
    <mat-datetimepicker #datetimePicker type="datetime" openOnFocus="true" timeInterval="5"></mat-datetimepicker>
    <input matInput formControlName="start" [matDatetimepicker]="datetimePicker" required autocomplete="false">
  </mat-form-field>
</form>
```
### Theming
```
@import '~@mat-datetimepicker/core/datetimepicker/datetimepicker-theme.scss';

// Using the $theme variable from the pre-built theme you can call the theming function
@include mat-datetimepicker-theme($theme);
```
@see [src/styles.scss](src/styles.scss)

