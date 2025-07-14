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

You can also assign a default value to a parameter. If no argument is provided during the call, the default is used. 
```php
function greet($name = "Guest") {
	echo "Hello, $name!";
}

greet(); // Output: Hello, Guest!
greet("John"); // Output: Hello, John!
```

Default parameters must be at the end of the parameter list. You can't put a defaulted parameter before a non-defaulted one. 

##### 4. Returning Values
You can make a function perform a computation and then return it using the `return` keyword. Returning: 

- Exits the function immediately
- Outputs a value back to the caller

```php 
function square($x) {
	return $x * $x;
}

echo square(5); // Outputs: 25
```

Returned values can be stored, printed, or passed into other functions. 

##### 5. Type Declarations
PHP also supports type declarations on parameters and return values for when you want the arguments as well as the returned value to be a particular type: 

```php 
function add(int $a, int $b): int {
	return $a * $b;
}
```

In the above code, `$a` and `$b` must be integers and the function will return an integer. If strict typing is not enabled, PHP will attempt to convert inputs to the declared type if possible. To force enforcement, you must include: 

```php 
declare(strict_types=1);
```

at the top of the file to prevent PHP from silently converting strings like `"3"` into integers. You can also set up manual validation and throw an error: 

```php 
function greet($name): string (
	if (!is_string($name)) {
		throw new InvalidArgumentException("Expected a string");
	}
	return "Hello, $name";
)
```

##### 6. Pass-by-Value vs. Pass-by-Reference
By default, PHP passes function arguments by value, which means that the function only works on a copy and won't modify the original: 

```php 
function double($x) {
	$x = $x * 2;
}

$a = 5;
double($a);
echo $a; // Still 5
```

If you want to modify the original variable, then you would use pass-by-reference by adding `&`:

```php 
function double(&$x) {
	$x = $x * 2;
}

$a = 5;
double($a);
echo $a; // Modified to 10
```

Use reference only when necessary because it creates side effects, which can reduce predictability. 

##### 7. Variable Scope
By default, variables that are declared inside a function are local, meaning that the don't exist outside it. If you want to access an external variable, you have three options: 

a) Pass it in: 

```php 
function addOne($x) {
	return $x + 1;
}
```

b) Use the `global` keyword: 

```php 
$x = 5;
function test() {
	global $x;
	$x++;
}
```

c) Use `static` to retain function-local state between calls

```php 
function counter() {
	static $count = 0;
	$count++;
	echo $count;
}
```

In the above case, each time you call `counter()`, `$count` is remembered.

##### 8. Anonymous Functions (Closures)

PHP allows functions without names that can be stored in variables and passed around: 

```php
$square = function($x) {
	return $x * $x;
};

echo $square(4); // 16
```

Closures can also capture variables from the surrounding scope using the `use` keyword: 

```php 
$multiplier = 3;
$triple = function($x) use ($multiplier) {
	return $x * $multiplier;
};

echo $triple(5); // 15
```

##### 9. Recursive Functions 

A recursive function calls itself. All recursion must have a base case (stop condition) or it causes infinite loops. Use recursion when a problem is defined in terms of smaller subproblems of the same type (e.g. traversing trees, summing ranges).

```php 
function factorial($n) {
	if ($n <= 1) return 1;
	return $n * factorial($n - 1);
}
```

##### 10. Higher-Order Functions

A higher-order function is one that either: 
1. Accepts another function as an argument 
2. Returns a function as its result

PHP supports both patterns via callable types, anonymous functions, and named function references. 

```php 
function process($x, $fn) {
	return $fn($x);
}

echo process(4, 'sqrt'); // gives the squareroot of 4, which is 2
```

Or with anonymous functions: 

```php 
echo process(4, function($n) { return $n * 3; }); // returns 12
```
#### Exercises

**1. Basic Output:**  Write a function `sayHello()` that prints "Hello, PHP".

```php 
function sayHello() { echo "Hello, PHP"; }
```

**2. Parameters:**  Write a function `multiply($a, $b)` that returns the product of two numbers.

```php 
function multiply($a, $b) { return $a * $b; }
```

**3. Default Parameter:**  Create a function `greetUser($name = "Anonymous")` that returns "Hi, [name]".

```php
function greetUser($name = "Anonymous") { echo "Hi, $name"; }
```

**4. Return Values:**  Write a function `cube($x)` that returns the cube of a number.

```php 
function cube($x) { return $x * $x * $x; }
```

**5. Type Declarations:**  Write `divide(float $a, float $b): float` that returns the division result.

```php 
function divide(float $a, float $b): float { return $a / $b; }
```

**6. Reference:**  Write `appendExclamation(&$str)` that adds "!" to the end of the input string, using reference.

```php 
function appendExclamation(&$str) { $str .= "!"; }
```

**7. Scope:**  Create a function `incrementCounter()` that uses a global variable `$count` and increments it.

```php

$count = 0;

function incrementCounter() { 
	global $count; 
	$count++;
}
```

**8. Closure:**  Create an anonymous function `$triple` that multiplies any input by 3 and invoke it.

```php 
$triple = function($x) { return $x * 3; }

echo $triple(5); // Output 15
```

**9. Recursive:**  Write a recursive function `sumToN($n)` that returns the sum of all integers from 1 to $n.

```php 
function sumToN($n) {
	if ($n <= 1) return 1;
	return $n + sumToN($n - 1); 
}
```

**10. Composite:**  Write `process($x, $fn)` where `$fn` is a function applied to `$x`. Call `process(4, 'sqrt')` and return the result.

```php 
function process($x, $fn) {
	return $fn($x);
}

echo process(4, 'sqrt');
```

