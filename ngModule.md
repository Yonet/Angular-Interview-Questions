* What is the purpose of NgModule?
  
  NgModule helps us to organize our components, directives and services into a logical unit, each focused on a feature.
  
  For example, we have 5 components in your project and that each component is dependent on other component or services or pipes then we   need to import them into the respective component. And, then repeat the same process for all other components. This will become         cumbersome to keep including on each of these components. This is where NgModules recuse us by importing everything to @NgModule which   will be available throughout the components under one module. 
  
* How do you decide to create a new NgModule?
  
  When we are dealing with medium or large apps, it includes discrete set of functionality. Administration, Dashboard, Bookings/Orders,   Promotions are all examples of areas of our apps that, when linked together, make our app. We basically breakdown our app into smaller   pieces called Features / Modules. 
  
  In the process of developing an app we might create a feature which we don't want to expose or create a feature which we want to lazy   loading when the user decides it is time to revisit the feature. NgModules helps us to separate our features to logical units and load   it when required.
 
* What are the attributes that you can define in an NgModule annotation?
* What is the difference between a module's forRoot() and forChild() methods and why do you need it?
  We all know that when a module provides a service and imported by a lazy loaded module, new instance of the service will be created by angular.
  Therefore, we usually try to avoid define services in modules that will be imported by many other module. However, there may be some cases which contradict this approach. Take a look at Angular RouterModule https://angular.io/guide/router#configuration

  RouterModule declares and exports some directives, e.g. router-outlet, routerLink, routerLinkActive etc.
  Also, it provides some services e.g. Router, ActivatedRoute etc. 
  Take a look at the source https://github.com/angular/angular/blob/master/packages/router/src/router_module.ts
  To avoid having multiple instances of services, RouterModule defines two methods, "forRoot" and "forChild". As the name suggests, "forRoot" method should be called only by root module, i.e. app.module, and forChild should be called by other feature modules. This way, you still get to use directives, components, pipes exported by this module and don't get new instances of services. 
  If you want to define such module yourself, you can do it as following

  ```ts
  @NgModule({
    declarations: [MyAwesomeComponent, MyCoolDirective],
    exports: [MyAwesomeComponent, MyCoolDirective]
  })
  export class MyAwesomeModule { 
    static forRoot(): ModuleWithProviders {
      return {
        ngModule: MyAwesomeModule,
        providers: [MyBrilliantService]
      }
    }
  }
  ```
* What would you have in a shared module?
  I would put directives, pipes, components and other modules that are used throughout my application and export them from this shared module. 
  This way, I would not have to declare/import same components/modules everywhere.
* What would you not put shared module?
  I would not put services in a shared module which may be imported by a lazy loaded module. When a lazy loaded module imports a module which provide a service,
  angular will create another instance of this service which may result in unexpected behaviors.
* What module would you put a singleton service whose instance will be shared throughout the application (e.g. ExceptionService andLoggerService)?
  I would create a core module and provide all the singleton services I have from this module. I would import this module only in app.module so that,
  all the feature modules, even the lazy loaded ones, would use same instances of the services.
* What is the purpose of exports in a NgModule?
  To make components/directives/pipes/modules available to other modules that import this module.
* Why is it bad if SharedModule provides a service to a lazy loaded module?

  This question arose in the Angular Module chapter when we discussed the importance of keeping providers out of the SharedModule.

  Suppose we had listed the UserService in the module's providers (which we did not). Suppose every module imports this SharedModule (which they all do).

  When the app starts, Angular eagerly loads the AppModule and the ContactModule.

  Both instances of the imported SharedModule would provide the UserService. Angular registers one of them in the root app injector (see above). Then some component injects UserService, Angular finds it in the app root injector, and delivers the app-wide singleton UserService. No problem.

  Now consider the HeroModule which is lazy loaded!

  When the router lazy loads the HeroModule, it creates a child injector and registers the UserService provider with that child injector. The child injector is not the root injector.

  When Angular creates a lazy HeroComponent, it must inject a UserService. This time it finds a UserService provider in the lazy module's child injector and creates a new instance of the UserService. This is an entirely different UserService instance than the app-wide singleton version that Angular injected in one of the eagerly loaded components.

  That's almost certainly a mistake.

  Prove it for yourself. Run the live example. Modify the SharedModule so that it provides the UserService rather than the CoreModule. Then toggle between the "Contact" and "Heroes" links a few times. The username goes bonkers as the Angular creates a new UserService instance each time.

  https://angular.io/docs/ts/latest/cookbook/ngmodule-faq.html#!#q-what-to-export
