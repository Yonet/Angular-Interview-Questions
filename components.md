## Components

#### What is the minimum definition of a component?

		import { Component } from '@angular/core';

		@Component({
			templateUrl: './minimum.component.html' // or
			template: ''
		})
		export class MinimumComponent {}

Note that:

* constructor is not requred, it is auto generated
* selector is not required, component can be accessed via router by class name
* template is required (either template or templateUrl)

#### What is the difference between a component and a directive?

There are three kinds of directives in Angular:

* components - directive with a template
* structural directives - changes DOM layout by adding and removing elements i.e. *ngFor
* attribute directives - changes appearance or behaviour of an element, component or another directive
(ngStyle for example)

so precisely:

* component uses @Component decorator, directive uses @Directive decorator
* component has template, directive has not

#### How do components comunicate with each other?

Types of communication:

* parent/child communication using @Input decorator and @Output decorator with EventEmitter
* communication using services and Angular dependency injection system
* communication via store (redux) which also uses Angular DI

#### How to create two way data binding in Angular?

To set up two way data binding one must use both () and [], so:

* `<component [(title)]="name"></component>` is the way to go
* `<component [title]="name" (titleChange)="name=$event"></component>` is also valid equivalent
* `<input [(ngModel)]="userName">` this a special case for form control binding

#### How would you create a component to display error messages throughout your application?

There are many possible ways, but let's say we want toastie to display an error. We do:

1. Create ErrorService which we inject everywhere from where we want to propagate error to display.
2. Create ToastieContainerComponent, inject service here and subscribe to errors. This component propagates
values to child componentand  manages its lifecycle.
3. Create presentational component ToastieComponent which displays toastie to user and gets values via @Input
from component.
4. Use ToastieContainerComponents somewhere in your app preferably in AppComponent.

#### What does lean component mean to you?

A lean component is a component which solely purpose is to display data to user. This means such component
delegates data fetching, bussiness logic, input validation etc. to other classes like models, services,
redux effects/actions etc. Lean component follows single responsibility principle.
