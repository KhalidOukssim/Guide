# Angular in details

## A/

### 1-Components

when we add a component We must add it to Modules in app.module.

selector: <joke></joke>

template: html or the link of html file

```typescript
@Component({
  selector: 'joke',
  template: `
  <h1>What did the cheese say when it looked in the mirror?</h1>
  <p>Halloumi (hello me)</p>`
})
```

### 2-String Interpolation

```html
<h1>{{emp.name}}</h1>
<!-- emp.name must be declared in typescript file --!>
```

### 3-data binding

```html
<div *ngFor="let emp of employees">
  <h4 class="card-title">{{emp.name}}</h4>
  <p class="card-text">{{emp.email}}</p>
</div>
<!-- employees is an array in typescript file --!>
```

```html
<p [hidden]="isExist()">{{emp.name}}</p>
<a class="btn btn-primary"
  (click)="toggle(emp)">Hiiii
</a>
<!-- isExist is a fct that return boolean declared in typescript file --!>
```

The way think about these two different ways of binding is in terms of inputs and outputs.
• With the [] we are binding to an input of a Component.
• With the () we are binding to an output of a Component.
This is what we call  one-way data binding, since data only flows one way, either into or out of a
component.
It is possible also to  simulate two-way data binding.

## B/

### 1-how to use ng

```
ng g component My // Creates MyComponent
```

By default all generated files go in into src\app\my-component, a folder called  my-componentis created
for us.

#### Directive

```
ng g directive My // Creates MyDirective
```

By default all generated files go in into src\app, no folder is created.

#### Pipe

```
ng g pipe My // Creates MyPipe
```

By default all generated files go in into src\app, no folder is created.

#### Service

```
ng g service MyService // Creates MyService
```

By default all generated files go in into src\app, no folder is created.

#### Class

```
ng g class MyClass // Creates MyClass
```

By default all generated files go in into src\app, no folder is created.

#### Interface

```
ng g interface MyInterface // Creates MyInterface
```

By default all generated files go in into src\app, no folder is created.

#### Enum

```
ng g enum MyEnum // Creates MyEnum
```



