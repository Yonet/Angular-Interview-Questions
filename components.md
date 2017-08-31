* What is the minimum definition of a component?

* What is the difference between a component and a directive?

    Component will have the template but directive wont. 
* How do components communicate with each other?

    1)Using @Input, @Output and EventEmitter
    
    2)Using Services and injecting them
* How do you create two way data binding in Angular?
    1) By using both Property binding and Event Binding both together at a time.
    2) By using [(ngModel)]     
* How would you create a component to display error messages throughout your application?

* What does a lean component mean to you?

Components don't fetch data from the server, validate user input, or log directly to the console. They delegate such tasks to services.
A component's job is to enable the user experience and nothing more. 
It mediates between the view (rendered by the template) and the application logic (which often includes some notion of a model). 
A good component presents properties and methods for data binding. It delegates everything nontrivial to services.
