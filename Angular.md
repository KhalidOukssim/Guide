# Angular

```
npm install -g @angular/cli
ng new name
ng serve -o
ng g c about
```

![](https://github.com/KhalidOukssim/Guide/tree/main/Images/Angular comp.JPG)

## 01 - postCreateComp.component.ts

```typescript
import {Component} from '@angular/core'

@Component({
    selector:'app-name', 
    templateUrl:'./htmlFile'
})
export class PostCreateComp{
    newPost='No Content'
    onAddPost(){
        this.newPost='Hi';
    }
}
```

poste.html

```html
<textarea [value]="newPost" #postInput></textarea>
<button (click)="onAddPost()"></button>
```

```typescript
import {FormsModule} from 'angular/forms'
imports:[
    FormsModule
]
//use ngModel in html
//==> <textarea   [(ngModel)]="entredValue"></textarea>
```

## 02 - Angular Materials

```typescript
*ngIf="condition;else condition" or use [hidden]
<ng-template #cmt></ng-template> //you can put cmt in your condition 
<div *ngFor="let post of array; index as i;trackby=functionName"> 
     
<div [ngSwitch]="a">
     <div *ngSwitchCase="'b'"></div>

[ngClass]="{
'glyphicon-star':isSelected,
'glyphicon-star-empty':!isSelected
}"
[ngStyle]="{
'backgroundColor':CanSave ? 'blue' : 'gray'
}"
ngModel name="first" #first="ngModel" //all info about a case in form
first.valid or first.touched...
<input required minlengt=4 maxlength=5 pattern="thing"
```

### a - Two-way Binding

```typescript
<input [(ngModel)]="email" (keyup.enter)="onKeyUp" />
    email="hello@gmail.com"
    onKeyUp{
        console.log(this.email)
    }
```

### b - pipe

```typescript
@pipe({
name:name
})
class ServicePipe implements PipeTransform{
transform(value:any,args?:any){
//code
}
}
```

### c - input and output

```typescript
@input() isfavorite:boolean
```

### d - hadow Dom

![](https://github.com/KhalidOukssim/Guide/tree/main/Images/shadow Dom.JPG)

## 03 - Forms

### a - ngForm & ngModelGroup

like ngModel just its refers to a form not an input

## 04 - Routing

```typescript
import {RouterModule} from '@angular/routes';
imports:[
    RouterModule.forRoot(
    [
        {path: '', component: Com1},
        {path: 'pathName1', component: Com2},
        {path: 'pathName2/:username', component: Com3},
        {path: '**', component: CompNotFound},//other router
    ])
]
```

### a - routerOutlet

```typescript
<router-outlet></router-outlet>
<a routerLink="pathName"></a>
<a [routerLink]="['pathName',pathName.id]"></a>
routerLinkActive="active current"
route.paramMap.subscribe(params =>{
    console.log(params);
});
```

### b - Query Parameters

```
<a [routerLink]="['pathName',pathName.id]"
[queryParams]="{page:1,order:'newest'}"
></a>
```

### c - Observable & SwitchMap Operator

