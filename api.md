* What does this line do:

```ts
@HostBinding('class.valid') isValid;
```

Binds a host element property (here, the CSS class valid) to a directive/component property (isValid).


* Why would you use renderer2 methods instead of using native element methods?

Renderer2 class is an abstraction provided by Angular to manipulate elements without touching directly. Using renderer service will provide us opportunity to be able to execute manipulations in non-DOM environments like native mobile, desktop and web worker rendering.

* How would you control size of an element on resize of the window in a component?
* What would be a good use for NgZone service?

The most common use of this service is to optimize performance when starting a work consisting of one or more asynchronous tasks that don't require UI updates or error handling to be handled by Angular. Such tasks can be kicked off via runOutsideAngular and if needed, these tasks can reenter the Angular zone via run.

* What are the bootstrap options for NgZone? Why would you use them? (Angular 5+)

- Provide your own `NgZone` instance.
- `zone.js` - Use default `NgZone` which requires `Zone.js`.
- `noop` - Use `NoopNgZone` which does nothing. You need to use async filter or manage change detection manually.

source:[https://github.com/angular/angular/commit/344a5ca#diff-0ef0b3df44ffd7a42aab5233a1a3defc]

* Why would you use renderer methods instead of using native element methods?

You are not sure what the context you are doing the rendering. You might be assuming the browser compilation and native DOM methods to be available but that might not be the case. It is better to be safe and let Angular handle the manupulation for elements.

* How would you protect a component being activated through the router?
  [Please correct me if I am wrong ]  By Defning gaurds in angular like CanActivate,CanActivateChild, CanDeactivate, CanLoad  source : [https://blog.thoughtram.io/angular/2016/07/18/guards-in-angular-2.html]
  Guards can be implemented in different ways, but after all it really boils down to a function that returns either Observable<boolean>, Promise<boolean> or boolean. In addition, guards are registered using providers, so they can be injected by Angular when needed.
  
* How would you insert an embedded view from a prepared `TemplateRef`?

