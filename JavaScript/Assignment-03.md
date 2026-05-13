# __03 📁JAVASCRIPT Assignment💻__ 

## 🔎Section A: Theory & Basics

### __01. What is variables in javascript?__


A variable is a _named container_ to store data in memory.

*3 ways to declare:*
var name = "Arun";   // old, function scoped, can redeclare
let age = 25;        // modern, block scoped, can update
const pi = 3.14;     // block scoped, can't update or redeclare
*Rules:*
1. Use `let` for values that change, `const` for values that don’t.
2. Names: letters, digits, `_`, `$`. Can’t start with digit. Case sensitive.
3. `var` is hoisted + function scoped. `let`/`const` are block scoped.

*In short*: Variables = labels for data. Prefer `const` by default, use `let` when you need to reassign.

### __2. What is the difference between declaration, initialization, and re-assignment?__

*Declaration*  
The act of creating a variable and registering its name in scope. No value is assigned yet.  
Example: `let age;`

*Initialization*  
The act of assigning a value to a variable for the _first time_.  
Example: `let age = 25;` or `age = 25;` after declaring

*Re-assignment*  
The act of changing the value of an already initialized variable to a new value.  
Example: `age = 30;`

### __3. What are let, var, and const? What is the difference between them?__

*`var`*  
A variable declaration that is function-scoped. Can be re-declared and re-assigned. Hoisted and initialized as `undefined`.

*`let`*  
A variable declaration that is block-scoped. Can be re-assigned but not re-declared in the same scope. Hoisted but not initialized — has Temporal Dead Zone.

*`const`*  
A variable declaration that is block-scoped. Cannot be re-assigned or re-declared. Must be initialized at declaration. Hoisted but not initialized — has Temporal Dead Zone.

*Quick rule*: Use `const` by default, `let` when you need to reassign, avoid `var`.

### __4. Create a greeting alert. (Hint: use prompt, variable message, and alert.__

*Greeting Alert – Code*
let name = prompt("Enter your name:");
let message = "Hello, " + name + "!";
alert(message);
*What it does:*
1. `prompt` asks the user for input and stores it in `name`
2. `message` variable combines the greeting text with the name
3. `alert` shows the message in a popup

### __5. What are the naming conventions in javascript__


*Rules – must follow:*
1. Can contain letters, digits, `_`, `$`
2. Cannot start with a digit
3. Case sensitive: `age` and `Age` are different
4. Reserved keywords like `let`, `if`, `for` not allowed

*Conventions – should follow:*
1. *camelCase* – for variables and functions: `firstName`, `getUserData`
2. *PascalCase* – for classes and constructors: `UserProfile`, `Date`
3. *UPPER_SNAKE_CASE* – for constants: `MAX_SIZE`, `API_KEY`
4. *Descriptive names* – `userAge` not `x`
5. *Boolean prefix* – start with `is`, `has`, `can`: `isLoggedIn`, `hasPermission`

*In short*: Use `camelCase` for most things, `PascalCase` for classes, `UPPER_CASE` for constants. Keep names clear and meaningful.

## 🔎Section B: Practical Problems

### __6. Create variables for age, city, and isStudent. Print them in one sentence.__

*Code:*
let age = 22;
let city = "Kochi";
let isStudent = true;

console.log("I am " + age + " years old, I live in " + city + ", and isStudent: " + isStudent);
*Output:*
I am 22 years old, I live in Kochi, and isStudent: true
*Template literal version:*
console.log(`I am ${age} years old, I live in ${city}, and isStudent: ${isStudent}`);

### __7. Swap the values of two variables using a temp variable. (Hint: let x = 11, let y = 5, swap the values so that x is 5 and y is 11)__ 

*Swap using temp variable:*
let x = 11;
let y = 5;

let temp = x;  // temp = 11
x = y;         // x = 5
y = temp;      // y = 11

console.log(x);  // 5
console.log(y);  // 11
*Steps:*
1. Store `x` in `temp`
2. Assign `y` to `x` 
3. Assign `temp` to `y`

### __8. Change a variable from number to string and print both values.__

*Code:*
let num = 42;
console.log("Number:", num, "Type:", typeof num);

let str = String(num);  // or num.toString()
console.log("String:", str, "Type:", typeof str);
*Output:*
Number: 42 Type: number
String: 42 Type: string
*In short*: Use `String(value)` or `value.toString()` to convert number to string. The original `num` stays a number, `str` holds the string version.

### __9. Combine firstName and lastName using template literals.__

*Code:*
let firstName = "John";
let lastName = "Doe";

let fullName = `${firstName} ${lastName}`;
console.log(fullName);  // John Doe
*Note*: Template literals use backticks `` ` `` and `${variable}` to insert values. Much cleaner than `"Hello " + firstName + " " + lastName`.

### __10. Identify valid and invalid variable names.__

*Valid variable names:*
1. `firstName` – letters, camelCase
2. `age2` – letters + digits, doesn't start with digit
3. `_count` – can start with `_`
4. `$price` – can start with `$`
5. `user_age` – underscores allowed
6. `isActive` – camelCase boolean style

*Invalid variable names:*
1. `2age` – cannot start with a digit
2. `first-name` – hyphens not allowed
3. `let` – reserved keyword
4. `user name` – no spaces allowed
5. `class` – reserved keyword
6. `@value` – `@` not allowed

*Rule*: Use letters, digits, `_`, `$` only. Can't start with digit. Can't use keywords.