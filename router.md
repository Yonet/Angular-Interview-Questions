#### What is the diffrence between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?

* forRoot creates a module that contains all the directives, the given routes, and the router service itself. 
* forChild creates a module that contains all the directives and the given routes, but does not include the router service. 
It registers the routers and uses the router service created at the root level. 
* This is important because location is a mutable global property. Having more than one object manipulating the location is not a good idea.

#### How does loadChildren property work?

```
const routes: Routes = [
  ...,
  { path: 'edit', loadChildren: 'app/edit/edit.module#EditModule' },
  ...
]
```
* In the above example, loadChildren tells the router to fetch the EditModule bundle assigned to it *when* the user visits '/edit' url. (To be more precise, it will ask the module loader to find and load it.)
* Router will get the router configuration from edit module.
* It merges EditModule router configuration with the main application configuration.
* Activate all the needed components.

#### Do you need a Routing Module? Why/not?
Yes if the user was expected to navigate between different URLs. The Routing Module interprets the browser's URL as an instruction to load a specific component and its view. The application has to have its main router configured and bootstraped by passing an array of routes to `RouterModule.forRoot()`, and since this returns a module, it has to be added to the `imports` meta property in the main application module. 

The RouterModule:

- defines routes
- adds router configuration to the module's imports
- re-exports RouterModule
- adds guard and resolver service providers to the module's providers


#### When does a lazy loaded module is loaded?

The `loadChildren` property is used by the Router to map to a bundle and lazy-load it. The router will take our `loadChildren` string and dynamically load in a module, add its routes as child routes to the configuration dynamically and then load the requested route. This will only happen when the route is first requested and the module will be immediately be available for subsequent requests.

Note that lazy-loaded modules should be removed from modules tehy were part of since they will be loaded on demand.


#### Below link doesn't work. Why? How do I fix it?
```
<div routerLink='product.id'></div>
```
The routerLink should specify a defined path in the routing configuration and the required path parameter (`product.id`). The code above tries to visit a specific product page, so it should be done using *Link Parameters Array*:

```
<div [routerLink]="['/product', product.id]"></div>
```

The above is correct in the case of having `product/:id` as a path in the application router configuration.

