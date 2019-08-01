#### Testing Questions:

* What are some of the different tests types you can write?

Isolated, shallow, integration, e2e.

* How do you mock a service to inject in an integration test?
* How do you mock a module in an integration test?
* How do you test a component that has a dependency to an async service?
* What is the difference between 'async()' and 'fakeAsync()'? 

async():

Wraps a test function in an asynchronous test zone. 
The test will automatically complete when all asynchronous calls within this zone are done. 
Can be used to wrap an inject call.

[Read more...](https://next.angular.io/api/core/testing/async)

fakeAsync(): 
Wraps a function to be executed in the fakeAsync zone:
  + microtasks are manually executed by calling flushMicrotasks(),
  + timers are synchronous, tick() simulates the asynchronous passage of time.
  
[Read more...](https://next.angular.io/api/core/testing/fakeAsync)
