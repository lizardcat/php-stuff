Functions are the most basic form of abstraction in PHP. They encapsulate behavior behind a name. you pass in inputs (parameters), run logic inside, and (optionally) return a result. You define the function once, and you can call it as many times as needed. 

##### 1. Function Declaration
In PHP, a function is declared using the `function` keyword, followed by the function name and a set of parentheses. Inside the parentheses go the parameters (if any), and the function body is enclosed in `{}`. 

```php 
function greet() {
	echo "Hello, world!";
}
```

In PHP, function names are not case-sensitive, so `GREET()` also works, though it is discouraged stylistically. 

##### 2. Parameters and Arguments

You can define parameters inside the parentheses: 

```php
function greet($name) {
	echo "Hello, $name!";
}
```

Each parameter behaves like a local variable inside the function. PHP supports any number of parameters, but they must be passed in the correct order unless default values are used. 

##### 3. Default Parameter Values


#### Exercises

**1. Basic Output:**  Write a function `sayHello()` that prints "Hello, PHP".

**2. Parameters:**  Write a function `multiply($a, $b)` that returns the product of two numbers.

**3. Default Parameter:**  Create a function `greetUser($name = "Anonymous")` that returns "Hi, [name]".

**4. Return Values:**  Write a function `cube($x)` that returns the cube of a number.

**5. Type Declarations:**  Write `divide(float $a, float $b): float` that returns the division result.

**6. Reference:**  Write `appendExclamation(&$str)` that adds "!" to a string in place.

**7. Scope:**  Create a function `incrementCounter()` that uses a global variable `$count` and increments it.

**8. Closure:**  Create an anonymous function `$triple` that multiplies any input by 3 and invoke it.

**9. Recursive:**  Write a recursive function `sumToN($n)` that returns the sum of all integers from 1 to $n.

**10. Composite:**  Write `process($x, $fn)` where `$fn` is a function applied to `$x`. Call `process(4, 'sqrt')` and return the result.