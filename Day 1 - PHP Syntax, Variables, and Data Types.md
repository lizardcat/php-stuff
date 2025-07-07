##### 1. PHP Syntax 
- Code is enclosed in `<?php ... ?>` tags
- Every statement ends with a semicolon
- Comments are either `//` or `#` for single-line and /* ... /  for multi-line

##### 2. Variables
- Declared with `$` followed b name. 
- Variables are case-sensitive
- They have to start with a letter or underscore

##### 3. Data Types 
- String: `"Hello"`, etc.
- Integer: `123`, `-56`
- Float/double: `3.14`
- Boolean: `true`, `false` 
- Array: `array(1, 2, 3)`, `['a' => 1, 'b' => 2]`
- Object: Instances of classes
- NULL: Variable with no value
- Resource: File hands, DB connections, etc. 

##### 4. Type Juggling
- PHP is loosely typed and can convert its types automatically: 
	- `'5' + 2` becomes `7`
	- `5 apples + 2` becomes `7`
	- `'apples' + 2` becomes `0 + 2`
##### 5. String Interpolation
- Double-quoted strings parse variables: `"$name"`
- Single-quoted strings don't: `'$name'`

##### 6. Constants 
- The are defined with either `const NAME = value;` or using `define('NAME`, value)`
- There are no `$` used with constants 
- Constants are global
- They are usually written in all-caps

##### Exercises 

###### 1. Write a PHP script that outputs your name and age on separate lines using `echo`:

```php 
echo "My name is Alex";
echo "<br>";
echo "I am 23 years old";
```

###### 2. Declare three variables: a string, an integer, and a float. Output them on one line: 

```php 
$name = "Alex";
$age = 23;
$weight = 79.55;

echo "My name is $name, I am $age years old, and I weigh $weight kg.";
```

###### 3. Write a function `getTypeDescription($var)` that uses gettype() and echo to describe a variable's type and value. 

```php
function getTypeDescription($var) {
    $type = gettype($var);
    echo "The variable is of type: $type and value: ";
    var_dump($var);
}
```

###### 4. Show the difference between using a double and single quotes when printing a variable inside a string.

```php
$var = "eggs & bacon";

echo "If you use a double quotes, your variable is parsed. See: $var";
echo "<br>";
echo 'If you use single quotes, then your variable won\'t be parsed. See: $var';
```

###### 5. Define a constant `SITE_NAME` and output it inside a sentence. 

```php
const SITE_NAME = "twitch.com";
echo "My favorite streaming website is " . SITE_NAME;
```

###### 6. Create a variable `$x = 0;`, test it in an if-statement and explain what happens. 
```php
$x = 0; 

if ($x === NULL) {
	echo "Please give \$x a value";
}
else {
	echo "The value of the variable is $x";
}

# The above code checks if $x has a value. If it does, then it simply prints out the value. If it doesn't, it asks the user to please give a value.
```

###### 7. Write a function that accepts any value and manually returns a string like "This is a string", "This is an integer", etc., without using `gettype()`. 

```php 
function checkType($var) {
	if (is_int($var)) {
		echo "This is an integer";
	} elseif (is_string($var)) {
		echo "This is a string";
	} elseif (is_bool($var)) {
		echo "This is a boolean";
	} elseif (is_float($var)) {
		echo "This is a float";
	} elseif (is_array($var)) {
		echo "This is an array";
	} elseif (is_null($var)) {
		echo "This is null";
	} else {
		echo "Unknown type";
	}
}
```