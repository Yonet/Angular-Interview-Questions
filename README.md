# Angular2-Interview-Questions

This file contains a number of Angular 2.0 interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [Animations Questions](#animations-questions)
  1. [Architecture Questions](#architecture-questions)
  1. [API Questions](#api-questions)
  1. [Template Questions](#template-questions)
  1. [Component Questions](#component-questions)
  1. [Component Interaction & State Management Questions](#component-interaction-&-state-management-questions)
  1. [Forms Questions](#forms-questions)
  1. [General Questions](#general-questions)
  1. [Structural Directives Questions](#structural-directives-questions)
  1. [Styling Questions](#styling-questions)
  1. [Services Questions](#services-questions)
  1. [Style Guide Questions](#style-guide-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)


#### General Questions:

* What did you learn about Angular 2.0 yesterday/this week?

#### Animations Questions:

#### Architecture Questions:

#### API Questions:

* What does this line do:

  ```
  @HostBinding('[class.valid]') isValid;
  ```
*

#### Template Syntax Questions:

* How can you add an active class to a selected element in a list component?
* What is a template variable. How would you use it?

#### Component Questions:

* What is the minimum definition of a component?

#### Component Interaction & State Management Questions:

* How would you pass data from a parent component to a child component?
* How would you pass data from a child component to a parent component?

#### Forms Questions:

#### NgModules Questions:

* What is the purpose of NgModule?
* How do you decide to create a new NgModule?
* What are the attributes that you can define in an NgModule annotation?
* What would you have in a shared module?
* What would you not put shared module?
* What module would you put a singleton service whose instance will be shared throughout the application (e.g. ExceptionService andLoggerService)?


#### Structural Directives Questions:

#### Styling Questions:

* How would you select a custom component to style it.

#### Services Questions:

#### Testing Questions:

#### Style Guide Questions:

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.


#### Lifecycle Hooks Questions:

#### Pipes Questions:

#### Routing Questions:


#### Observables/RxJS Questions:

* What is the difference between an observable and a promise?
* How would you implement a [brush behavior](https://bl.ocks.org/mbostock/34f08d5e11952a80609169b7917d4172) using rxjs? 
* How would you implement a color picker with rxjs?

#### TypeScript Questions:

#### Security Questions:



#### Coding Questions:

* What would these components render?

```
import {Component, ContentChildren, Directive, Input, QueryList} from '@angular/core';
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
* What's your favorite feature of Angular 2.0?
* How do you like your coffee?


#### Contributors:
* [Aysegul Yonet](https://developers.google.com/experts/people/aysegul-yonet)
