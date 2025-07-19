PHP is loosely typed. Variables are not bound to specific types, but type control is often necessary for correctness.
##### 1. Type Juggling

PHP automatically converts types when needed. 

```php
$sum = "10" + 5; // $sum = 15
```

Common implicit conversions include: 
- String to int/float when doing math
- Boolean conversion in conditions
- Numeric string to int in comparisons

##### 2. Explicit Type Casting

You can explicitly force conversion: 

```php
$intVal = (int)"123.45"; // 123
$floatVal = (float)"10"; // 10.0
$boolVal = (bool)0; // false
```
##### 3. Type Checking Functions

PHP provides built-in functions to inspect types, such as: 

- `is_int()`: Checks if a variable is an integer
- `is_string()`: Checks if variable is string
- `is_bool()`: Checks if variable is boolean
- `is_array()`: Checks if variable is array
- `is_null()`: Checks if variable is null
- `is_object()`: Checks if variable is object
##### 4. `gettype()`

This is a function that returns a string describing the type of a value: 

```php
echo gettype(100); // "integer"
```
##### 5. `var_dump()`

This displays the type and value information. It is preferred for debugging: 

```php 
var_dump([1, 2, "a"]);
```
##### 6. Strict Typing

You can enable strict typing by adding this to file start: 

```php
declare(strict_types=1);
```

This enforces function parameter and return type constraints. 

```php 
function add(int $a, int $b): int {
	return $a + $b;
}
```

Without strict typing, using `"10"` as a value would be coerced into `10`. With strict types, this causes a TypeError. 
##### 7. Type Declarations in Functions

PHP supports type declarations for: 

- Scalar types: `int`, `float`, `bool`, `string`
- Compound types: `array`, `object`, `callable`
- Nullable types: `?int`, `?string`, etc.

E.g.: 
```php
function greet(?string $name): string {
	return "Hello, " . ($name ?? "Guest");
}
```

### **Exercises**

##### 1. Write a function `add(int $a, int $b): int` with strict typing. Call it with both integers and strings and observe the result.

```php
declare(strict_types=1);

function add(int $a, int $b): int {
	return $a + $b;
}
```

##### 2. Use `gettype()` and `var_dump()` to inspect a variable assigned different values.



##### 3. Cast a float to an integer and explain the result.



##### 4. Write a script that checks if a variable is `int`, `float`, or `string` using `is_*()` functions.



##### 5. Create a nullable string parameter function that returns a greeting.



##### 6. Write a function that accepts only arrays. Pass a non-array and handle the error.



##### 7. Demonstrate type juggling by adding a string `"100"` to a number and echo the result.



##### 8. Enable strict typing in a file and pass wrong types to a function.



##### 9. Show the behavior of `var_dump()` on an object, array, and boolean.



##### 10. Evaluate and explain the output of:
```php
var_dump("0" == false);
var_dump("0" === false);
```

