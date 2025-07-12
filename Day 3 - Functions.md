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