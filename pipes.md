* What is a pure pipe?
* What is an async pipe?
* What kind of data can be used with async pipe?
* How do you create a custom pipe?

* How does async pipe prevents memory leeks?

Async pipe knows about the lifespan of the component and unscubscribes from the observable if necessary. 

* What is the difference between pure and impure pipes?

  `Pure Pipes:`

  * Input parameters value determine the output so if input parameters don’t change the output doesn’t change.
  * Can be shared across many usages without affecting the output result.
  * Pure pipes are pure functions that are easy to test.

  `Impure Pipes:`

  * Cannot use the input value to determine if the output will change.
  * Cannot be shared because the internal state can be affected from outside.
