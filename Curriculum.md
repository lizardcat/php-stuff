### **Phase 1: Core Foundations (Days 1–7)**

Build operational clarity on PHP syntax, control, and primitive types.

- **Day 1:** _Syntax, Variables, Types_
    
    - Scalars, strings, constants, interpolation rules, basic output
        
- **Day 2:** _Control Structures_
    
    - if, elseif, else, switch, loops (while, do-while, for, foreach), break, continue
        
- **Day 3:** _Functions_
    
    - Declarations, parameters (default, reference), return types, scope
        
- **Day 4:** _Operators_
    
    - Arithmetic, assignment, comparison, logical, string, ternary, null coalescing
        
- **Day 5:** _Type Handling_
    
    - Type juggling, casting, `is_*()` functions, `gettype()`, `var_dump()`, strict typing
        
- **Day 6:** _Arrays: Indexed & Associative_
    
    - Creation, access, iteration, nesting, `array_*` functions
        
- **Day 7:** _Superglobals & Input Handling_
    
    - `$_GET`, `$_POST`, `$_SERVER`, `$_REQUEST`, sanitation
        

---

### **Phase 2: Intermediate Constructs (Days 8–15)**

Transition to program structure, modularity, and standard library fluency.

- **Day 8:** _String Functions_
    
    - `strlen`, `strpos`, `substr`, `str_replace`, heredoc/nowdoc, multiline handling
        
- **Day 9:** _Array Functions_
    
    - `array_map`, `array_filter`, `array_reduce`, sorting, merging, slicing
        
- **Day 10:** _Loops + Data Processing Patterns_
    
    - Iterator patterns, multidimensional arrays, nested control
        
- **Day 11:** _Error Handling_
    
    - `try`, `catch`, `finally`, `Exception`, custom exceptions
        
- **Day 12:** _File I/O_
    
    - `fopen`, `fread`, `fwrite`, `file_get_contents`, `file_put_contents`, CSV parsing
        
- **Day 13:** _Date & Time Handling_
    
    - `DateTime`, `strtotime`, formatting, timezones
        
- **Day 14:** _Built-in Functions Mastery_
    
    - `var_dump`, `print_r`, `empty`, `isset`, `unset`, `die`, `exit`
        
- **Day 15:** _Form Processing & Basic Validation_
    
    - POST/GET parsing, HTML forms, basic validation, response echoing
        

---

### **Phase 3: Object-Oriented PHP (Days 16–22)**

Introduce class-based structure and OOP idioms.

- **Day 16:** _Classes, Objects, and Properties_
    
    - `class`, `new`, public/private/protected, `this`, constructors
        
- **Day 17:** _Methods and Encapsulation_
    
    - Getters/setters, visibility, method chaining
        
- **Day 18:** _Inheritance and Polymorphism_
    
    - `extends`, `parent::`, overriding, constructors in hierarchies
        
- **Day 19:** _Interfaces and Abstract Classes_
    
    - `interface`, `implements`, `abstract`, contract enforcement
        
- **Day 20:** _Static, Final, and Class Constants_
    
    - `static` methods/properties, `self::`, `::class`, `final`
        
- **Day 21:** _Namespaces and Autoloading_
    
    - `namespace`, `use`, PSR-4 basics, `spl_autoload_register`
        
- **Day 22:** _Traits and Composition_
    
    - `trait`, use-cases, conflict resolution
        

---

### **Phase 4: State, Persistence, and Request Context (Days 23–26)**

Handle session, cookies, server context, and form state.

- **Day 23:** _Sessions and Cookies_
    
    - `session_start`, `$_SESSION`, `setcookie`, expiry, security flags
        
- **Day 24:** _Server Variables and Routing_
    
    - `$_SERVER`, path parsing, method detection
        
- **Day 25:** _HTTP Headers and Redirects_
    
    - `header()`, status codes, caching headers, content-type control
        
- **Day 26:** _File Uploads and Validation_
    
    - `$_FILES`, `move_uploaded_file`, mime-type validation, size checks
        

---

### **Phase 5: Applied Development (Days 27–30)**

Solidify patterns through applied projects and cleanup.

- **Day 27:** _Mini MVC Without Framework_
    
    - Request routing, controller logic, view separation
        
- **Day 28:** _Simple CRUD App with Filesystem Persistence_
    
    - Form input → file storage → display → update/delete
        
- **Day 29:** _Security Patterns_
    
    - Input sanitization, output escaping, CSRF tokens, session hardening
        
- **Day 30:** _Code Review, Refactor, Optimization_
    
    - Code audits, benchmarking, avoiding globals, side-effects, dead paths

### **Phase 6: Production Readiness (Days 31–33)**

Introduce tooling and structural maturity for real-world deployment.

- **Day 31:** _Composer & Dependency Management_
    
    - `composer.json`, `require`, PSR autoloading, vendor structure
        
- **Day 32:** _Unit Testing with PHPUnit_
    
    - Installing PHPUnit, writing tests, assertions, mocks, test coverage
        
- **Day 33:** _Configuration Management_
    
    - `php.ini` essentials, `ini_get`, `ini_set`, `.env` handling via libraries like `vlucas/phpdotenv`