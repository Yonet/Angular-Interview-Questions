# Angular-Interview-Questions

This file contains a number of [Angular](https://angular.io/) interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

A developer is perfectly able to use Angular to build applications without being able to answer all of these questions. Addition to having a source for interview questions, my intention is to encourage interested developers to think about these questions. I regularly teach Angular workshops. Oftentimes I do not get enough questions due to limited exposure working with the framework. These questions are the ones I personally needed to answer, to be able lead a team developing our first Angular production application at Autodesk A360.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

* [Animations Questions](#animations-questions)
* [Architecture Questions](#architecture-questions)
* [API Questions](#api-questions)
* [Template Questions](#template-syntax-questions)
* [Component Questions](#component-questions)
* [Component Interaction & State Management Questions](#component-interaction--state-management-questions)
* [Forms Questions](#forms-questions)
* [General Questions](#general-questions)
* [NgModules Questions](#ngmodules-questions)
* [Observables RxJS Questions](#observables-rxjs-questions)
* [Performance Questions](#performance-questions)
* [Pipes Questions](#pipes-questions)
* [Router Questions](#router-questions)
* [Services Questions](#services-questions)
* [Structural Directives Questions](#structural-directives-questions)
* [Styling Questions](#styling-questions)
* [Style Guide Questions](#style-guide-questions)
* [Testing Questions](#testing-questions)
* [TypeScript Questions](#typescript-questions)
* [JavaScript Questions](#javascript-questions)
* [Coding Questions](#coding-questions)
* [Fun Questions](#fun-questions)


#### General Questions:

* What did you learn about Angular yesterday/this week?
* What are some of the reasons you would choose to use Angular in your project?
* What did you like about working with Angular?
* How do you keep your Angular code more readable and maintainable?
* What does testable code mean to you in context of Angular?
* What does reusable code mean to you in context of Angular?

#### Animations Questions:

* How do you define transition between two states in Angular?
* How do you define a wildcard state?

#### Architecture Questions:

* What is a good use case for ngrx/store?
* What is a good use case for ngrx/entity?
* Can you talk about a bug related to a race condition, how to solve it and how to test it?
* What is the difference between a smart/container component and dumb/presentational component? What is a good use case example? What are the advantages?

#### API Questions:

* What does this code do:

```ts
@HostBinding('class.valid') isValid;
```

```html
<div *ngIf='someObservableData | async as data; else loading'>{{data}}</div>

<ng-template #loading>
  Loading Data...
</ng-template>
```

* Why would you use renderer methods instead of using native element methods?
* How would you control size of an element on resize of the window in a component?
* What would be a good use for NgZone service?
* What are the bootstrap options for NgZone? Why would you use them? (Angular 5+)
* How would you protect a component being activated through the router?
* How would you insert an embedded view from a prepared `TemplateRef`?
* What is the difference between @ViewChild() and @ContentChild()

#### Template Syntax Questions:

* How can you add an active class to a selected element in a list component?
* What is a template variable. How would you use it?
* What is the difference of using a property binding verses a function binding on a template?
* What happens if you subscribe to a data source multiple times with async pipe?
* what is the difference between ng-content, ng-container and ng- template?
* When you create a data-binding in Angular, are you working with attributes or properties? What is the difference anyway?
* When can you omit the brackets in template binding? 

#### Component Questions:

* What is the minimum definition of a component?
* What is the difference between a component and a directive?
* How do components communicate with each other?
* How do you create two way data binding in Angular?
* How would you create a component to display error messages throughout your application?
* What does a lean component mean to you?

#### Component Interaction & State Management Questions:

* How would you pass data from a parent component to a child component?
* How would you pass data from a child component to a parent component?
* Which components will be notified when an event is emitted?
* Tell me about the different ways how you would get data to your components from a service and talk about why would you use one way vs the other?
* How would you use cached data?

#### Forms Questions:

* When do you use template driven vs model driven forms? Why?
* How do you submit a form?
* What's the difference between `NgForm`, `FormGroup`, and `FormControl`? How do they work together?
* What's the advantage of using `FormBuilder`?
* How do you add form validation to a form built with `FormBuilder`?
* What's the difference between `dirty`, `touched`, and `pristine` on a form element?
* How can you access validation errors in the template to display error messages?
* What is async validation and how is it done?

#### NgModules Questions:

* What is the purpose of NgModule?
* How do you decide to create a new NgModule?
* What are the attributes that you can define in an NgModule annotation?
* What is the difference between a module's forRoot() and forChild() methods and why do you need it?
* What would you have in a shared module?
* What would you not put shared module?
* What module would you put a singleton service whose instance will be shared throughout the application (e.g. ExceptionService andLoggerService)?
* What is the purpose of exports in a NgModule?
* What is the difference between exports and declerations in NgModule?
* Why is it bad if SharedModule provides a service to a lazy loaded module?

#### Services Questions:

* What is the use case of services?
* How are the services injected to your application?
* How do you unit test a service with a dependency?
* Why is it a bad idea to create a new service in a component like the one below?

```ts
let service = new DataService();
```

#### Structural Directives Questions:

* What is a structural directive?
* How do you identify a structural directive in html?
* When creating your own structural directives, how would you decide on hiding or removing an element? What would be the advantages or disadvantages of choosing one method rather than the other?

#### Style Guide Questions:

* What are some of the Angular Style Guide suggestions you follow on your code? Why?
* Is it important to have a style guide? Why/not?

#### Styling Questions:

* How would you select a custom component to style it.
* What pseudo-class selector targets styles in the element that hosts the component?
* How would you select all the child components' elements?
* How would you select a css class in any ancestor of the component host element, all the way up to the document root?
* What selector force a style down through the child component tree into all the child component views?
* What does :host-context() pseudo-class selector targets?
* What does the following css do?

```css
:host-context(.theme-light) h2 {
  background-color: red;
}
```

#### Lifecycle Hooks Questions:

* What is the possible order of lifecycle hooks.
* When will ngOnInit be called?
* How would you make use of ngOnInit()?
* What would you consider a thing you should be careful doing on ngOnInit()?
* What is the difference between ngOnInit() and constructor() of a component?
* What is a good use case for ngOnChanges()?


#### Observables RxJS Questions:

* What is the difference between an observable and a promise?
* What is the difference between an observable and a subject?
* What are some of the angular apis that are using observables?
* How would you cache an observable data?
* How would you implement a multiple api calls that needs to happen in order using rxjs?
* What is the difference between switchMap, concatMap and mergeMap?
* How would you make sure an api call that needs to be called only once but with multiple conditions. Example: if you need to get some data in multiple routes but, once you get it, you can reuse it in the routes that needs it, therefor no need to make another call to your backend apis.
* How would you implement a [brush behavior](https://bl.ocks.org/mbostock/34f08d5e11952a80609169b7917d4172) using rxjs?
* How would you implement a color picker with rxjs?
* If you need to respond to two different Observable/Subject with one callback function, how would you do it?(ex: if you need to change the url through route parameters and with prev/next buttons).
* What is the difference between `scan()` vs `reduce()` ?

#### Performance Questions:

* What are some of the things that you pay attention to, to make sure your angular application is performant?
* What tools would you use to find a performance issue in your code?
* What tools have you used to improve the performance of your application?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.
* Have you seen Jeff Cross's NgCruise talk on performance?

#### Pipes Questions:

* What is a pure pipe?
* What is an async pipe?
* What kind of data can be used with async pipe?
* How do you create a custom pipe?
* How does async pipe prevents memory leeks?
* What is the difference between pure and impure pipes?

#### Router Questions:

* What is the difference between RouterModule.forRoot() vs RouterModule.forChild()?  Why is it important?
* How does loadChildren property work?
* Do you need a Routing Module? Why/not?
* When does a lazy loaded module is loaded?
* Below link doesn't work. Why? How do I fix it?

```html
<div routerLink='product.id'></div>
```

* Can you explain the difference between ActivatedRoute and RouterState?
* How do you debug router?
* Why do we need route guards?
* What is a RouterOutlet?

#### Security Questions:


#### Testing Questions:

* How do you mock a service to inject in a unit test?
* How do you mock a module in a unit test?

#### TypeScript Questions:

* Why do you need type definitions?
* How would you define a custom type?
* What is the difference between an Interface and a Class?
* First line below gives compile error, second line doesn't. Why?

```ts
someService.someMethod(x);
someService['someMethod'](x);
```

* What are Discriminated union types?
* How do you define Object of Objects type in typescript?
* How can you capture the 'type' the user provides (e.g. number), so that we can use that information later.

#### JavaScript Questions:

* Explain the difference between var, let and const key words.
* Could you make sure a const value is garbage collected?
* Explain Object.assign and possible use cases.
* Explain Object.freeze and possible use cases.
* Explain the code below. How many times the createVal function is called?

```ts
function createVal(){
  return Math.random();
};

function fun( val =  createVal()){
  // Do something with val...
}

fun();
fun(5);

```
* What is the spread operator doing in this function call? Seriously!

```
doStuff(...args);
```

#### Coding Questions:

* What would these components render?

```ts
import { Component, ContentChildren, Directive, Input, QueryList } from '@angular/core';

@Directive({selector: 'pane'})
export class Pane {
  @Input() id: string;
}

@Component({
  selector: 'tab',
  template: `
    <div>panes: {{serializedPanes}}</div>
  `
})
export class Tab {
  @ContentChildren(Pane) panes: QueryList<Pane>;
  get serializedPanes(): string { return this.panes ? this.panes.map(p => p.id).join(', ') : ''; }
}

@Component({
  selector: 'example-app',
  template: `
    <tab>
      <pane id="1"></pane>
      <pane id="2"></pane>
      <pane id="3" *ngIf="shouldShow"></pane>
    </tab>
    <button (click)="show()">Show 3</button>
  `,
})
export class ContentChildrenComp {
  shouldShow = false;
  show() { this.shouldShow = true; }
}
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Who inspires you in the angular community?
* Do you have any pet projects? What kind?
* How did you design the architecture of your project?
* What's your favorite feature of Angular?
* What is your least favorite thing about Angular? (Please share your thoughts by making a pull request to [angularFeelings](https://github.com/Yonet/Angular-Interview-Questions/blob/master/angularFeelings.md))
* How do you like your coffee?
* If you could decide on a new feature for angular, what would it be?

#### Contributors:
* [Ayşegül Yönet](https://developers.google.com/experts/people/aysegul-yonet)
* [Mohamad Atieh](https://github.com/MohamadAtieh)
* [Jay Kan](https://github.com/JayKan)
* [Matt Carpenter](https://github.com/mattcarp)
* [Ryan Chenkie](https://github.com/chenkie)
* [Shyam Chen](https://github.com/Shyam-Chen)
* [Josep Sayol](https://github.com/jsayol)
* [Tiep Phan](https://github.com/tieppt)
* [Igor Fesenko](https://github.com/Ky7m)
* [Stephan](https://github.com/styopdev)
* [Bhanu Chamakuri](https://github.com/bhanu7755)
* [Nanda](https://github.com/vivek4321)
* [Meow Zedong](https://github.com/therealmeowzedong)
* [Benjamin Cabanes](https://github.com/bcabanes)
* [Bunyamin Coskuner](https://github.com/bnymncoskuner)
* [Ha Hoang](https://github.com/sau-lanvy)
* [Merve Ağca](https://github.com/merveagca)
* [Ahmet Zeybek](https://github.com/ahmetzeybek)
* [Marek Sławiński](https://github.com/mslawins)
* You?
