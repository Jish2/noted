---
updated: 2025-09-30T20:05
created: 2025-09-30T19:08
---
#language/javascript 

alternative syntax for defining functions

examples:
```js
const foo = () => {};

// callback
function bar(callback) {
    callback();
};

bar(() => {
    console.log("this is a callback")
});

// will output: "this is a callback"
```

with [[typescript]]:
```ts
type Foo = () => void;
const foo: Foo = () => {};

type Bar = (param: int) => int;
const bar: Bar = (param) => { return param; };

// inline typed
const foobar = (param: int): int => { return param; };
```

### caveats
- no [[hoisting]] compared to `function` keyword defined functions