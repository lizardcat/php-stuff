
## **Exercises**

**1. Basic URL Handling**: Write a script that echoes `$_GET['user']`. Visit the URL with a query string like `?user=Admin`.


**2. Conditional Input Check**: Use `isset()` to check if a `$_POST['comment']` exists. If it doesn’t, print `"No comment provided."`.


**3. Request Method Guard**: Create a form that sends a POST request. In the handler, reject any GET requests by checking `$_SERVER['REQUEST_METHOD']`.


**4. Echo Server Info**: Print the current script name (`PHP_SELF`), request method, and full URI using `$_SERVER`.


**5. Input Echo with Sanitization**: Send `name` and `email` via POST. Sanitize and print them using `htmlspecialchars()` and `FILTER_SANITIZE_EMAIL`.


**6. Email Validator**: Use `filter_input()` with `FILTER_VALIDATE_EMAIL`. Display `"Valid email"` or `"Invalid email"` based on result.


**7. Integer Validator**: Create a form that takes an age. Validate with `FILTER_VALIDATE_INT`. Reject non-integers.


**8. Unified Input Script**: Accept `name` from either GET or POST. Use `$_REQUEST`. Log the request type source with `$_SERVER['REQUEST_METHOD']`.


**9. Header Output**: Create a script that detects user agent (`HTTP_USER_AGENT`) and prints different messages for Chrome vs Firefox.


**10. Query Parameter Exploder**: From a query like `?id=42&lang=en&mode=test`, iterate through all `$_GET` keys and values using `foreach`, and print each key/value pair.
