* How would you select a custom component to style it.
* What pseudo-class selector targets styles in the element that hosts the component?
* How would you select all the child components' elements?
* How would you select a css class in any ancestor of the component host element, all the way up to the document root?
* What selector force a style down through the child component tree into all the child component views?

* What does :host-context() pseudo-class selector targets?

 It works just like the function form of :host(). It looks for a CSS class in any ancestor of the component host element, all the way up to the document root. It's useful when combined with another selector.
