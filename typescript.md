* Why do you need type definitions?


* How would you define a custom type?


* What is the difference between an Interface and a Class?


* First line below gives compile error, second line doesn't. Why?


* What are Discriminated union types?

https://basarat.gitbooks.io/typescript/content/docs/types/discriminated-unions.html
https://github.com/Microsoft/TypeScript/pull/9163

* How do you define Object of Objects type in typescript?

* How can you capture the 'type' the user provides (e.g. number), so that we can use that information later.

```ts
function identity<T>(arg: T): T {
    return arg;
}
```
[Read more...](https://www.typescriptlang.org/docs/handbook/generics.html)
