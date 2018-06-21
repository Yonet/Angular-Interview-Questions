* What is the difference between an observable and a promise?

    Both Promises and Observables provide us with abstractions that help us deal with the asynchronous nature of our applications. However, there are important differences between the two:
    - Observables can define both the setup and teardown aspects of asynchronous behavior.
    - Observables are cancellable.
    - Moreover, Observables can be retried using one of the retry operators provided by the API, such as retry and retryWhen. On the other hand, Promises require the caller to have access to the original function that returned the promise in order to have a retry capability.



* What is the difference between `scan()` vs `reduce()` ?

  - Scan will show all values emitted on source observable.
  - Reduce will show only the final value emitted on source observable.

    ```js
    var obsScan = Observable.from([1,2,3,4,5,6]);
    var count1 = obsScan.scan((acc, one) => acc + one, 0);
    count1.subscribe(x => {
        console.log('scan shows incremental total', x);
    });

    var obsReduce = Observable.from([1,2,3,4,5,6]);
    var count2 = obsReduce.reduce((acc, one) => acc + one, 0);
    count2.subscribe(x => {
        console.log('reduce shows only total', x);
    });
    ```

    Output :

    <pre>
    scan shows incremental total 1
    scan shows incremental total 3
    scan shows incremental total 6
    scan shows incremental total 10
    scan shows incremental total 15
    scan shows incremental total 21
    reduce shows only total 21
    </pre>

    Video example : 
    
    <a href="https://www.youtube.com/watch?v=myEeo2rZc3g" target="_blank"><img src="https://img.youtube.com/vi/myEeo2rZc3g/0.jpg" alt="drawing" style="width:300px;"/></a>
