* Explain the difference between var, let and const key words.
* Could you make sure a const value is garbage collected?
  Yes, but...
  Assigning an object or array as a constant means that value will not be able to be garbage collected until that constant’s lexical scope goes away, as the reference to the value can never be unset. 
  That may be desirable, but be careful if it’s not your intent!
  [Read more...](https://books.google.com/books?id=iOc6CwAAQBAJ&pg=PT24&lpg=PT24&dq=keyle+simpson+Assigning+an+object+or+array+as+a+constant+means+that+value+will+not+be+able+to+be+garbage+collected+until+that+constant%E2%80%99s+lexical+scope+goes+away,&source=bl&ots=7v7iLPetjx&sig=t8flr1cB-DlnFaBMhlCcewpW2bs&hl=en&sa=X&ved=0ahUKEwjZ-czuteDbAhWaHTQIHeGlAhgQ6AEINDAC#v=onepage&q=keyle%20simpson%20Assigning%20an%20object%20or%20array%20as%20a%20constant%20means%20that%20value%20will%20not%20be%20able%20to%20be%20garbage%20collected%20until%20that%20constant%E2%80%99s%20lexical%20scope%20goes%20away%2C&f=false)
* Explain Object.assign and possible use cases.
* Explain Object.freeze and possible use cases.
* Explain the code below. How many times the createVal function is called?

```ts
function createVal(){
  return Math.random();
};

function fun( val =  createVal()){
  // Do something with val...
}

fun();
fun(5);

```
* What is the spread operator doing in this function call? Seriously!

```
doStuff(...args);
```

With the spread operator we can avoid apply all together and simply call the function with the spread operator. [Read more...](https://davidwalsh.name/spread-operator).
Note: although there it looks simpler, I think this is less readable at the moment since more developers are familiar with apply. 
