Superglobals are built-in global arrays in PHP that are available in all scopes. These arrays are always accessible and you don't need to use `global` or pass them as arguments. 

The most important superglobals for input handling are: 

- `$_GET`
- `$_POST`
- `$_REQUEST`
- `$_SERVER`
- `$_COOKIE`
- `$_SESSION`
- `$_FILES`
- `$_ENV`

Today, I'll only focus on `$_GET`, `$_POST`, `$_REQUEST`, and `$_SERVER`.

#### 1. `$_GET`

- It's an associative array of variables passed to the current script via the URL query string. 
- It is used with `method="get"` in HTML forms. 
- It's parameters appear in the URL. For example: `example.php?name=John&age=30`

```php
echo $_GET['name']; // Outputs "John"
```

#### 2. `$_POST`

- This is an associative array of variables passed to the current script via the `HTTP POST` method. 
- The data is not visible in the URL 
- It's suitable for sensitive or large data (e.g. passwords, comments, form submissions)

#### 3. `$_REQUEST`

- Contains the contents of `$_GET`, `$_POST`, and `$_COOKIE` combined
- Should be used with caution. Prefer `$_GET` or `$_POST` explicitly. 

#### 4. `$_SERVER`

- Contains information about headers, paths, and script locations. 
- Useful for request method detection and environment control. 

Some common entries for `$_SERVER` include: 

- `$_SERVER['REQUEST_METHOD']`: Returns 'GET' or 'POST'
- `$_SERVER[''PHP_SELF']`: Filename of the currently executing script
- `$_SERVER['HTTP_USER_AGENT']`: Client's browser & platform information
- `$_SERVER['SERVER_NAME']`: Host name

For example: 

```php 
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
	echo "Handling POST request.";
}
```

#### 5. Detecting and Handling Input

Always check if input exists before using it: 

```php 
if (isset($_GET['name'])) {
	$name = $GET['name'];
}
```

Avoid assuming keys exist to prevent undefined index warnings. 

#### 6. Sanitizing Input

Raw user input is dangerous for a variety of reasons, so you should use built-in filters. 

##### a. Manual Sanitization (basic)

```php
$name = htmlspecialchars($_POST['name']); // Escapes HTML entities
```

##### b. `fitler_input()` Function 

```php 
$email = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL);
```

The options for the function include: 

- `FILTER_SANITIZE_STRING`: Remove tags & encode special chars
- `FILTER_SANITIZE_EMAIL`: Remove invalid characters from email 
- `FILTER_VALIDATE_EMAIL`: Validate email format
- `FILTER_VALIDATE_INT`: Validate integer

Example with validation: 

```php
$age = filter_input(INPUT_GET, 'age', FILTER_VALIDATE_INT);
if ($age === false) {
	echo "Invalid age.";
}
```

#### 7. Practical Form Example

HTML Form (form.html):

```html
<form action='process.php' method="post">
	Name: <input type="text" name="name">
	Email: <input type="text" name="email">
	<input type="submit">
</form>
```

PHP Processor (process.php):

```php 
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
	$name = htmlspecialchars($_POST['name']);
	$email = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL);

	echo "Name: $name<br>";
	echo "Email: $email";
}
```
## **Exercises**

**1. Basic URL Handling**: Write a script that echoes `$_GET['user']`. Visit the URL with a query string like `?user=Admin`.

```php 
echo $_GET['user']
```

**2. Conditional Input Check**: Use `isset()` to check if a `$_POST['comment']` exists. If it doesn’t, print `"No comment provided."`.

```php 
if (!isset($_POST['comment'])) {
	echo "No comment provided";
}
```

**3. Request Method Guard**: Create a form that sends a POST request. In the handler, reject any GET requests by checking `$_SERVER['REQUEST_METHOD

HTML Form (form.html):

```http
<form action='process.php' method="post">
	Name: <input type="text" name="name">
	Email: <input type="text" name="email">
	<input type="submit">
</form>
```

PHP Processor (process.php):

```php 
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
	$name = htmlspecialchars($_POST['name']);
	$email = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL);

	echo "Name: $name<br>";
	echo "Email: $email";
}
```

**4. Echo Server Info**: Print the current script name (`PHP_SELF`), request method, and full URI using `$_SERVER`.

```php
echo $_SERVER['PHP_SELF'];
echo $_SERVER['REQUEST_METHOD'];
echo $_SERVER['HTTP_USER_AGENT'];
```


**5. Input Echo with Sanitization**: Send `name` and `email` via POST. Sanitize and print them using `htmlspecialchars()` and `FILTER_SANITIZE_EMAIL`.

```php
if (isset($_SERVER['REQUEST_METHOD'] === 'POST'])) {
	$name = htmlspecialchars($_POST['name']);
	$email = filter_input(INPUT_POST, 'email', FILTER_SANITIZE_EMAIL);

	echo "Name: $name<br>";
	echo "Email: $email";
}
```

**6. Email Validator**: Use `filter_input()` with `FILTER_VALIDATE_EMAIL`. Display `"Valid email"` or `"Invalid email"` based on result.

```php
if (filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL)) {
	echo "Valid email";
} else {
	echo "Invalid email";
}
```

**7. Integer Validator**: Create a form that takes an age. Validate with `FILTER_VALIDATE_INT`. Reject non-integers.

```php
<form method="POST"> 
	Age: <input type="number" name="age">
	<input type="submit">
</form>

<?php 
if ($_SERVER_$['REQUEST_METHOD'] === 'POST') {
	$age = filter_input(INPUT_POST, 'age', FILTER_VALIDATE_INT);
    if ($age === false) {
        echo "Invalid entry: non-integer!";
    } else {
        echo "Age accepted: $age";
    }
}
```

**8. Unified Input Script**: Accept `name` from either GET or POST. Use `$_REQUEST`. Log the request type source with `$_SERVER['REQUEST_METHOD']`.

```php
if ($_SERVER['REQUEST_METHOD'] === "POST") {
	echo $_POST["name"] . " was logged with a POST method";
} else {
	echo $_GET["name"] . " was logged with a GET method";
}
```

**9. Header Output**: Create a script that detects user agent (`HTTP_USER_AGENT`) and prints different messages for Chrome vs Firefox.

```php 
$browser = $_SERVER['HTTP_USER_AGENT'];

if (str_contains($browser, 'Firefox')) {
    echo "You are using Firefox!";
} elseif (str_contains($browser, 'Chrome')) {
    echo "You are using Chrome!";
}
```

**10. Query Parameter Exploder**: From a query like `?id=42&lang=en&mode=test`, iterate through all `$_GET` keys and values using `foreach`, and print each key/value pair.

```php
foreach ($_GET as $key => $value) {
	echo "$key: $value<br>";
}
```