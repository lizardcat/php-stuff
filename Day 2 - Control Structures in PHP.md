
##### 1. If / Else / Elseif

This one is fairly straightforward so I won't dwell on it for too long. But basically, it's used to perform conditional branching. It executes different blocks of code based on the result of one or more boolean expressions:  

```php
if ($a > 10) {
	// code
} elseif ($1 == 10) {
	// code 
} else {
	// code
}
```

##### 2. Switch 

This one takes an initial variable, then runs it through several cases to find the correct match. It efficiently handles multiple values of a single variable. It is ideal when testing equality against discrete known values. It also includes a default action at the end that runs if no cases match: 

```php
switch ($value) {
	case 1: 
		// code
		break;
	case 2: 
		// code
		break; 
	case 3: 
		// code
		break;
	default: 
		// code
}
```

##### 3. While Loop 

Again, fairly straightforward. While a certain condition is happening, do XYZ. It only executes a block of code if a condition remains true. There is a also usually a counter. Here's an example: 

```php 
while ($i < 10) {
	// code 
	$i++;
}
```

##### 4. Do...While 

Do XYZ as long as certain condition is true. This is like an inverse version of a standard `while` loop that accomplishes the same thing but guarantees that the loop body is executed at least once. It is useful when user input or one execution is required before validating. 

```php 
do { 
	// code
	$i++;
} while ($i < 10);
```

##### 5. For Loop 

This is best sued when the number of iterations is known in advance. It features three parts: an initialization that runs once before the loop starts, a condition that is checked before each iteration, and an increment that runs after each iteration:

```php
for (initialization; condition; increment) {
	// loop body
}
```

##### 6. Foreach Loop 

This one is used for arrays typically. It iterates over arrays and objects. It is the cleanest way to access each element in an array without using indexes manually: 

```php 
foreach ($array as $value) {
	// use $value
}
```

Or alternatively: 

```php
foreach ($array as $key => $value) {
	// use $key and $value
}
```

##### 7. Break / Continue

**Break**: This immediately terminates the nearest enclosing loop or `switch`:

```php 
for ($i = 1; $i <= 10; $i++) {
	if ($i == 5) break; 
	echo $i . " ";
}

// Output: 1 2 3 4
```

**Continue**: This skips the current iteration and proceeds to the next one: 

```php 
for ($i = 1; $i <= 5; $i++) {
	if ($i === 3) continue; 
	echo $i . " ";
}

// Output: 1 2 4 5
```

##### 8. Ternary Operator
The purpose of this is to function as a shortcut for `if/else` when assigning values or expressions. The structure looks like: 

```php 
$var = (condition) ? value_if_true: value_if_false;
```

##### 9. Null Coalescing Operator

This assigns a default if a variable/index is null or not set: 

```php 
$var = $possiblyNullValue ?? $defaultValue
```

#### Exercises

##### 1. If/Else: Write a function `isEven($num)` that returns "Even" or "Odd"

```php
function isEven($num) {
	if ($num % 2 == 0) {
		echo "Even";
	} else {
		echo "Odd";
	}
}
```

##### 2. Switch: Write a switch block that takes a string `day` and prints whether it's a weekday or weekend
```php 
$day = "Monday";

switch ($day) {
	case "Monday":
	case "Tuesday":
	case "Wednesday":
	case "Thursday":
	case "Friday":
		echo "Weekday";
		break;
	case "Saturday":
	case "Sunday":
		 echo "Weekend";
		 break;
	default:
		echo "Invalid entry";
}
```

##### 3. While: Print numbers 1 through 10 using a `while` loop

```php
$i = 1; 
while ($i <= 10) {
	echo $i . " ";
	$i++;
}
```

##### 4. Do...While: Create a loop that prints a message at least once, even if the condition is false. 

```php 
$tally = 0;
do {
	echo "Printing at least once!";
	$tally++;
} while ($tally < 1);
```

##### 5. For: Print the first 10 square numbers using a `for` loop:

```php 

for ($i = 1; $i <= 10; $i++) {
	echo ($i * $i) . " ";
}
```

##### 6. Foreach: Given an array of fruits, print them in a list with their index

```php 
$fruits = ["apples", "oranges", "melons", "bananas", "mangoes", "kiwis"];

foreach ($fruits as $index => $fruit) {
	echo "$index: $fruit";
	echo "<br>";
}
```

##### 7. Break / Continue: Loop from 1 to 20; skip even numbers using `continue`, stop the loop if the number is greater than 15 using `break`

```php 
for ($i = 1; $i <= 20; $i++) {
	if ($i % 2 == 0) continue;
	if ($i == 15) break;
	echo $i . " ";
}
```

##### 8. Ternary: Given a variable `$score`, return "Pass" if it's >= 50, else "Fail"
```php
$score = 50;
$result = ($score >= 50) ? "Pass" : "Fail";
echo $result;
```

##### 9. Null Coalescing: Simulate getting a value from a request array `$req['username`']; if it's not set, default to "anonymous"

```php
$name = $_GET['username'] ?? 'anonymous';

echo "Hello " . $name;
```