## **Exercises**

**1. Length Measurement**: Print the length of:
- `"Hello"`
- `"こんにちは"` using both `strlen()` and `mb_strlen()`.

**2. Substring Extraction**: From the string `"The quick brown fox"`, extract:
- `"quick"`
- Last 3 characters
- First 3 characters

**3. Replace Operation**: Replace `"cat"` with `"dog"` in the string `"The cat sat on the mat"`.

**4. Case Conversion**: Convert `"php is great"` to:
- All uppercase
- Title case

**5. Whitespace Cleanup**: Given `"\n\t Hello World! \r\n"`, remove all leading and trailing whitespace. Show before and after.

**6. Interpolation Contrast**: Using a variable `$lang = "PHP"`, print `"I love PHP"` using:
- Single quotes
- Double quotes
- Heredoc
- Nowdoc

**7. Search with `strpos()`**: Given the string `"This is a test"`, find:
- Position of `"test"`
- Position of `"is"` (note: appears twice)
- Behavior when search fails (e.g. `"xyz"`)

**8. Explode/Implode Workflow**: Convert the CSV string `"red,green,blue"` into an array. Then rebuild it using `implode()` with a `" | "` separator.

**9. User Input Sanitization**: Given `$_GET['comment'] = "<script>alert(1)</script>"`, echo the sanitized version using `htmlspecialchars()`.

**10. Email Templating**: Using Heredoc, create an email template with:
- A dynamic `$name`
- A `$date`
- Output the final email content