
An array in PHP is a data structure that stores multiple values in a single variable. PHP arrays are ordered maps -- keys mapped to values. They can behave as: 

- Indexed arrays: keys are integers, automatically assigned
- Associative arrays: keys are strings
- Multidimensional arrays: arrays of arrays

Syntax for indexed array is as follows: 

```php
$colors = ["red", "green", "blue"];
```

or you can use the `array()` function as follows: 

```php
$colors = array("red", "green", "blue");
```

If you want to access the elements, you can use the index: 

```php
echo $colors[0]; // red
```

You can also append an element to the end by using: 

```php
$colors[] = "yellow"; // appended at the end
```

##### Associative Arrays

These are arrays with keys that are manually assigned as strings: 

```php 
$user = [
	"name" => "Alice",
	"age" => 18,
	"email" => "alice@example.com"
];
```

You access the values by using the key: 

```php
echo $user["name"]; // Alice
```

Adding or modifying a key: 

```php 
$user["status"] = "active";
$user["age"] = 31;
```

##### Multidimensional Arrays

These are arrays that contain other arrays as elements: 

```php

$matrix = [
	[1, 2, 3], 
	[4, 5, 6]
]; 

echo $matrix[1][2]; // 6
```

You can also have multidimensional arrays with associative layers: 

```php
$users = [
	[
		"name" => "Alice",
		"email" => "alice@example.com"
	],
	[
		"name" => "Bob",
		"email" => "bob@example.com"
	]
];

echo $user[0]["email"]; // alice@example.com
```

##### Array Functions 

Some examples of array functions include: 

`count($arr)` this returns the number of elements in an array: 

```php
count([1, 2, 3]); // 3
```

`arraypush($arr, $val1, $val2)` adds an element to the end of an existing array (`$arr`):

```php
array_push($colors, "purple", "orange");
```

`array_pop($arr)` removes the last element in the array: 

```php
$last = array_pop($colors);
```

`array_keys($arr)` returns all the keys in an array. 

`array_values($arr)` returns all the values. 

`in_array($needle, $arr)` checks if a value exists. 

##### Iterating Over Arrays

You can iterate over an array using a `foreach` loop. For example, here is how to do it with an indexed array: 

```php
$nums = [1, 2, 3];
foreach ($nums as $num) {
	echo $num;
}
```

To do this in an associative array, here is an example: 

```php
foreach ($user as $key => $value) {
	echo "$key: $value";
}
```

##### Array Destructuring

You can destructure an array into another array: 

```php
$rgb = ["red", "green", "blue"];
[$r, $g, $b] = $rgb;

echo $g; // green 
```

##### Spread Operator

The spread operator combines arrays or passes array values as arguments: 

```php
$arr1 = [1, 2];
$arr2 = [...$arr1, 3, 4]; // [1, 2, 3, 4] 
```
## Exercises

###### 1. **Indexed Array:** Create an array of 5 city names. Print the third one.

```php 
$cityNames = ["Nairobi", "Kisumu", "Arusha", "Nakuru", "Mombasa"];

echo $cityNames[2];
```

###### 2. **Associative Array:** Create a user profile with `name`, `email`, `is_admin`. Print the email.

```php
$userProfile = ["name" => "Alex", "email" => "araza@google.com", "is_admin" => true];

echo $userProfile["email"];
```

###### 3. **Add/Remove:** Add a new city to your cities array. Remove the last city.

```php

$cityNames[] = "Dodoma";
array_pop($cityNames);

```

###### 4. **Loop:** Loop through your cities and print each one in uppercase.

```php
foreach ($cityNames as $city) {
	echo strtoupper($city);
}
```

###### 5. **Count:** Count how many keys are in your user profile.

```php 

$count = 0;

foreach ($userProfile as $key => $value) {
    $count++;
}; 

echo $count;
```

###### 6. **Search:** Check if `"admin"` is a value in the user profile.

```php
if (array_key_exists("is_admin", $userProfile)) {
	echo "'admin' is in the array";
} else {
	echo "'admin' is not a value in the array";
}
```

###### 7. **Multidimensional:** Create a list of 2 products, each with `name` and `price`. Print the price of the second product.

```php 
$products = [
	["name" => "Laptop", "price" => 1200],
	["name" => "Phone", "price" => 800]
];

echo $products[1]["price"];

```

###### 8. **Destructuring:** Destructure an array `["apple", "banana", "cherry"]` into three variables. Print the second one.

```php 
$fruits = ["apple", "banana", "cherry"];

[$a, $b, $c] = $fruits;

echo $b;
```
###### 9. **Keys/Values:** Get all keys from the user profile and print them as a list.

```php
foreach ($userProfile as $key => $value) {
	echo $key;
	echo "</br>";
}
```

###### 10. **Spread:** Merge two arrays: `["a", "b"]` and `["c", "d"]` using the spread operator.

```php
$array1 = ["a", "b"];
$array2 = [...$array1, "c", "d"];
```