* What is the use case of services?
* How are the services injected to your application?
* How do you unit test a service with a dependency?
* Why is it a bad idea to create a new service in a component like the one below?
```
let service = new DataService();
```
That's a bad idea for several reasons including:

Our component has to know how to create a DataService. If we ever change the DataService constructor, we'll have to find every place we create the service and fix it. Running around patching code is error prone and adds to the test burden.

We create a new service each time we use new. What if the service should cache data and share that cache with others? We couldn't do that.

We're locking the component into a specific implementation of the DataService. It will be hard to switch implementations for different scenarios. Can we operate offline? Will we need different mocked versions under test? Not easy.

