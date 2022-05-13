## JS Functions: Declare vs. Express

Oh, JavaScript... That majestic, elusive beast we developers try to tame.. (I mostly fail).
In my newbie quest for JS knowledge, I came across this concept of "declaring" a function vs "expressing" it. Whaaaat?  🤔 

I did what I always do. I googled. And then I googled some more. I fell down a rabbit hole of articles and official docs and tweets. And this (in summary) is what I came up with.

**A function declaration:**

```
function calcRectArea(width, height) {
  return width * height;
}

console.log(calcRectArea(5, 6));
// expected output: 30

```
A valid function declaration must always begin with `function`, as a var declaration is supposed to begin with `var`.

vs.

**A function expression:**

```
const getRectArea = function(width, height) {
  return width * height;
};

console.log(getRectArea(3, 4));
// expected output: 12
```
Very similar to the function declaration syntax, but we can omit the function name, in order to create an anonymous function. 
The logic is then stored in `getRectArea` and can be called using that.
 
## "OK, but is there actually any difference?" Glad you asked!
![Glad you asked!](https://media.giphy.com/media/l4FGC3sZppT0imaty/giphy.gif)

### It's all about that hoisting

Function declarations in JavaScript are "hoisted". What that means is that functions that are declared, are made available "at the top" of the code; giving them global scope or at least bumping them up, at the top of the enclosing function. 

In reality, function declarations will be loaded before any other piece of code is executed. So the following is made possible:
```
hoisted(); // logs "foo" even when it's called BEFORE the declaration

function hoisted() {
  console.log('foo');
}
```
However, function expressions are **not** hoisted,  and this would produce an error:
```
notHoisted(); // TypeError: notHoisted is not a function

var notHoisted = function() {
   console.log('bar');
};
```
##  Why would anyone use a function expression over a declaration?

### It's all about location and timing
You need to consider what the function's purpose is, how and where in your code you plan to use it. 
Do you need to access it globally or perhaps just as an argument for another function? Will you reuse it? Or is it just a one-time thing?

Some use cases:

**IIFEs [ immediately invoked function expressions ]:**
This is a function that is dynamically declared at runtime, at the precise moment that it is needed/invoked.  Use it and then throw it away!

```
(function() {
    console.log('This is my first blog post!')
})();
```

For a very detailed list of IIFE use cases you can check out  [this article](https://mariusschulz.com/blog/use-cases-for-javascripts-iifes) (I guess it's out of this article's scope... get it? 😂 )

**Callbacks [a function as an argument for another function]:**

```
button.addEventListener('mouseover', function(event) {
    console.log('Click that button!!!')
})
```
## In Summary:
When you don't need to access a function globally, go with a function expression. It's best to use it ad-hoc, even let it remain anonymous, limit its scope, and keep your code clean and lean. Otherwise, go with a function declaration.

PS.  [I spotted a record of someone mentioning a performance difference between declaration and expression, depending on the browser/javascript engine they used.](https://stackoverflow.com/questions/28185860/function-declaration-vs-expression-from-a-performance-point-of-view) However, I haven't tried it myself, so I take it with a grain of salt... 🤷🏻‍♀️

Disclaimer: This blog is not an expert guide, just my attempt to make sense of stuff. If you spot any glaring mistakes or have any feedback at all, please let me know. 

Now, on to the next one!

![Spongebob and Patrick say Hooray](https://media.giphy.com/media/TdfyKrN7HGTIY/giphy.gif)


## References:

-  [MDN Function Declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) 

- [MDN Function Expression ](https://developer.mozilla.org/en-US/docs/web/JavaScript/Reference/Operators/function) 

-  [MDN Callback Function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function) 

-  [W3Schools JS Hoisting](https://www.w3schools.com/js/js_hoisting.asp) 

- [Callback and Anonymous functions in JavaScript](https://medium.com/@tonyparkerkenz/callback-and-anonymous-functions-in-javascript-8849d57f5ce9)

- [Function Declarations vs. Function Expressions](https://medium.com/@mandeep1012/function-declarations-vs-function-expressions-b43646042052)

- [When to use a function declaration vs. a function expression](https://www.freecodecamp.org/news/when-to-use-a-function-declarations-vs-a-function-expression-70f15152a0a0/)

- [Use Cases for JavaScript's IIFEs](https://mariusschulz.com/blog/use-cases-for-javascripts-iifes)

- [What is a Callback Function in JavaScript?](https://www.freecodecamp.org/news/what-is-a-callback-function-in-javascript/)


