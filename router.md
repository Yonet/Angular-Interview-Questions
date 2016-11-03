What is the diffrence between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?

* forRoot creates a module that contains all the directives, the given routes, and the router service itself. 
* forChild creates a module that contains all the directives and the given routes, but does not include the router service. 
It registers the routers and uses the router service created at the root level. 
* This is important because location is a mutable global property. Having more than one object manupilating the location is not a good idea.
