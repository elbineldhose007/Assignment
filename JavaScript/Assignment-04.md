# __📁04.JAVASCRIPT Assignment – Operators💻__

## 🔎Section A – Basic Questions

### __1.What are operators in JavaScript?__

Got it, no flowcharts.

*Operators in JavaScript* are symbols that perform operations on values/variables and return a result.

You use them to do math, assign values, compare things, combine logic, etc.

*Common ones:*

1. *Arithmetic*: `+`, `-`, `_`, `/`, `%`, `__`  
   Example: `10 + 5` gives `15`

2. *Assignment*: `=`, `+=`, `-=`, `_=`  
   Example: `let x = 5; x += 2;` now `x` is `7`

3. *Comparison*: `==`, `===`, `!=`, `>`, `<`, `>=`, `<=`  
   Example: `5 === "5"` gives `false`

4. *Logical*: `&&`, `||`, `!`  
   Example: `true && false` gives `false`

5. *Unary*: `typeof`, `++`, `--`, `!`  
   Example: `typeof 42` gives `"number"`

6. *Ternary*: `condition ? trueValue : falseValue`  
   Example: `age >= 18 ? "adult" : "minor"`

Think of operators as the action words. Operands are the nouns, operators tell them what to do.
### __2.	What is the difference between arithmetic operators and assignment operators?__

Got it, keeping it text only.

*Arithmetic operators* do calculations and give you a new value. They don't change the original variables unless you explicitly assign the result.

Example: `10 + 5` gives `15`. `a _ b` multiplies `a` and `b`. Common ones: `+`, `-`, `_`, `/`, `%`, `*_`, `++`, `--`.

*Assignment operators* store a value into a variable. They always update the variable on the left.

Example: `x = 10` puts `10` into `x`. `x += 5` is shorthand for `x = x + 5`, so it adds 5 and stores it back into `x`. Common ones: `=`, `+=`, `-=`, `_=`, `/=`.

*Key difference*: Arithmetic = "calculate this". Assignment = "save this into the variable".

`let result = 8 / 2;` uses both. `/` is arithmetic to get `4`, `=` is assignment to save it in `result`.
### __3.	Explain the purpose of comparison operators with examples.__

*Comparison operators* compare two values and return a boolean: `true` or `false`. 

You use them to make decisions, filter data, run code conditionally, and control loops.

*The main ones:*

1. *`==` equal* - checks if values are same after type conversion  
   `5 == "5"` gives `true`

2. *`===` strict equal* - checks if values AND types are same, no conversion  
   `5 === "5"` gives `false`, `5 === 5` gives `true`

3. *`!=` not equal* - true if values differ after conversion  
   `10 != "8"` gives `true`

4. *`!==` strict not equal* - true if values OR types differ  
   `10 !== "10"` gives `true`

5. *`>` greater than*  
   `7 > 3` gives `true`

6. *`<` less than*  
   `2 < 9` gives `true`

7. *`>=` greater than or equal*  
   `5 >= 5` gives `true`

8. *`<=` less than or equal*  
   `4 <= 3` gives `false`

*Used in real code:*
let age = 20;

if (age >= 18) {

  console.log("You can vote");  // runs because 20 >= 18 is true
}

let password = "abc123";

if (password === "abc123") {

  console.log("Access granted");  // true, strict match
}

let score = 85;

console.log(score > 90);  // false

*Rule of thumb*: Use `===` and `!==` by default. `==` and `!=` do weird type coercion and cause bugs.

### __4.What is the difference between == and === in JavaScript?__

*`==` is loose equality*. It compares values but does type conversion first.  

*`===` is strict equality*. It compares values AND types with no conversion.

*Key difference: type coercion*

5 == "5"     // true – string "5" gets converted to number 5

5 === "5"    // false – number vs string, different types

0 == false   // true – false becomes 0

0 === false  // false – number vs boolean

null == undefined  // true – special case in JS

null === undefined // false – different types

"" == 0      // true – empty string becomes 0  
"" === 0     // false – string vs number
*How `==` coerces:*
1. If comparing number and string, convert string to number

2. If boolean involved, convert boolean to number: `true`→1, `false`→0  

3. `null` and `undefined` are only equal to each other

4. Objects get converted to primitives

*When to use which:*

Use `===` 99% of the time. It's predictable and safer. 

if (userInput === "yes") { }  // good

Use `==` only if you intentionally want type coercion, like checking for null-ish:

if (value == null) { }  // true for both null and undefined

*Rule of thumb*: Default to `===`. It prevents weird bugs like `"0" == false` being `true`.
### __5.	What is the difference between != and !==?__

*`!=` is loose not equal*. It checks if values are different after doing type conversion.  
*`!==` is strict not equal*. It checks if values OR types are different, no conversion.

They're just the opposite of `==` and `===`.

*Examples:*
5 != "5"     // false – "5" becomes 5, so 5 != 5 is false

5 !== "5"    // true – number vs string, types differ

0 != false   // false – false becomes 0, so 0 != 0 is false  

0 !== false  // true – number vs boolean, types differ

null != undefined  // false – special case, they're considered equal

null !== undefined // true – different types

"10" != 10   // false – string converts to number

"10" !== 10  // true – string vs number

*How to think about it:*
- `!==` asks: "Are these different in value OR type?" 

- `!=` asks: "After I force them to be the same type, are the values different?"

*When to use:*

Use `!==` by default. Same reason you use `===`: it avoids surprise coercion.

if (status !== "complete") { }  // good, exact check

// This could bite you:

if (userId != 0) { }  // true for 0, false, "", "0", etc due to coercion

*Rule of thumb*: `!==` is safer and more predictable.
### __6.	What are logical operators? Explain &&, ||, and !.__

*Logical operators* work with boolean values and are used to combine or invert conditions. They return either `true`/`false` or one of the original operands.

*The 3 main ones:*

1. *`&&` AND* - Returns `true` only if both sides are true  

   If the first value is falsy, it stops and returns that value. Otherwise returns the second value.
   
   true && true       // true

   true && false      // false

   5 > 3 && 10 < 20   // true, because both are true
   
   const name = "Sam";

   name && console.log(name);  // logs "Sam" if name is truthy

2. *`||` OR* - Returns `true` if at least one side is true  

   If the first value is truthy, it stops and returns that value. Otherwise returns the second value.
   
   true || false      // true

   false || false     // false

   let user = null;

   let displayName = user || "Guest";  // "Guest", because user is falsy

3. *`!` NOT* - Inverts the boolean value  

   Converts to boolean, then flips it.
   
   !true              // false

   !false             // true

   !0                 // true, because 0 is falsy

   !"hello"           // false, because "hello" is truthy
   
   let loggedIn = false;

   if (!loggedIn) { } // runs because !false is true

*Truthy/Falsy matters*: In JS, `false`, `0`, `""`, `null`, `undefined`, `NaN` are falsy. Everything else is truthy.

*Common use:*
let age = 20;

let hasID = true;

if (age >= 18 && hasID) {

  console.log("Entry allowed");  // both must be true
}

let role = "";
if (role === "admin" || role === "mod") {

  console.log("Has permissions");  // either one works
}

if (!user) {
  console.log("No user found");  // runs if user is null/undefined/false
}
*Short-circuiting*: `&&` and `||` stop evaluating once the result is known. That's why `user && user.name` won't error if `user` is `null`.
### __7.	What is the purpose of the modulus (%) operator?__

*`%` modulus* returns the remainder after division. 

It doesn't give you how many times one number fits into another. It gives you what's left over.

*Basic math:*

10 % 3    // 1, because 10 / 3 = 3 remainder 1

15 % 5    // 0, because 15 / 5 = 3 remainder 0

7 % 2     // 1, because 7 / 2 = 3 remainder 1
*Common uses:*

1. *Check if a number is even or odd*
   let num = 8;

   if (num % 2 === 0) {

     console.log("Even");  // runs, 8 % 2 is 0
   }
   
   7 % 2  // 1, so odd

2. *Cycle through values / wrap around*  

   Useful for loops, arrays, clock math

   let index = 0;
   index = (index + 1) % 3;  // cycles: 0 -> 1 -> 2 -> 0 -> 1...
   
   let hour = 14;

   hour % 12  // 2, converts 24h to 12h time

3. *Get every Nth item*

   for (let i = 1; i <= 10; i++) {

     if (i % 3 === 0) {

       console.log(i);  // prints 3, 6, 9
     }
   }
4. *Limit a value to a range*

   137 % 100  // 37, keeps just the last 2 digits

*Note*: With negative numbers, the result takes the sign of the left operand in JS.

-10 % 3   // -1

10 % -3   // 1

*Rule of thumb*: If you need "remainder" or "every Nth time", use `%`.
### __8.	What is the increment operator? Explain pre-increment and post-increment.__

*Increment operator `++`* adds 1 to a variable. 

There are two versions, and the difference is _when_ the value is returned vs updated.

*1. Pre-increment `++x`*  
Adds 1 first, then returns the new value.

let a = 5;

let b = ++a;  // a becomes 6, then b gets 6

console.log(a);  // 6

console.log(b);  // 6

*2. Post-increment `x++`*  
Returns the current value first, then adds 1.

let a = 5;

let b = a++;  // b gets 5, then a becomes 6

console.log(a);  // 6

console.log(b);  // 5

*Side by side:*

let x = 3;

console.log(++x);  // 4, increment then print

console.log(x);    // 4

let y = 3;

console.log(y++);  // 3, print then increment  

console.log(y);    // 4


*Where it matters:*

In a standalone statement, both do the same thing:

i++;  // same result as ++i here

But inside expressions, order matters:

let nums = [10, 20, 30];

let i = 0;

console.log(nums[i++]);  // prints 10, then i becomes 1

console.log(nums[++i]);  // i becomes 2, then prints 30

*Rule of thumb*: Use `i++` in loops by default. Use `++i` only when you specifically need the incremented value right away in the same expression. 


There's also decrement `--` which works the exact same way but subtracts 1.
### __9.	What is the decrement operator?__

*Decrement operator `--`* subtracts 1 from a variable.

It works exactly like `++` but in reverse. There are two versions:

*1. Pre-decrement `--x`*  
Subtracts 1 first, then returns the new value.

let a = 5;

let b = --a;  // a becomes 4, then b gets 4

console.log(a);  // 4

console.log(b);  // 4

*2. Post-decrement `x--`*  

Returns the current value first, then subtracts 1.

let a = 5;

let b = a--;  // b gets 5, then a becomes 4

console.log(a);  // 4

console.log(b);  // 5

*Side by side:*

let x = 3;

console.log(--x);  // 2, decrement then print

console.log(x);    // 2

let y = 3;

console.log(y--);  // 3, print then decrement  

console.log(y);    // 2

*Common use: counting down in loops*

for (let i = 5; i > 0; i--) {

  console.log(i);  // prints 5, 4, 3, 2, 1
}
*Rule of thumb*: `x--` returns the old value then decreases. `--x` decreases then returns the new value. 


In a standalone line, `i--` and `--i` do the same thing. The difference only shows up when you use the value in the same expression.

### 10.	What is operator precedence in JavaScript?

*Operator precedence* decides which operations run first when you have multiple operators in one expression.

Same idea as PEMDAS/BODMAS in math, but JS has way more operators.

*High precedence runs first, low precedence runs last.*

*Examples:*
2 + 3 * 4     // 14, not 20. * has higher precedence than +

              // So it's 2 + (3 * 4) = 2 + 12 = 14

10 - 4 / 2    // 8, not 3. / before -

              // 10 - (4 / 2) = 10 - 2 = 8

5 > 3 && 2 < 4  // true. > and < run before &&

// (5 > 3) && (2 < 4) → true && true → true

*General order from highest to lowest:*

1. *Grouping* `()` - forces things to run first

2. *Increment/Decrement* `++`, `--` 

3. *Arithmetic* `*_`, then `_`, `/`, `%`, then `+`, `-`

4. *Comparison* `<`, `>`, `<=`, `>=`, `===`, `!==`

5. *Logical* `&&` before `||`

6. *Assignment* `=`, `+=`, etc - happens last

*Tricky ones:*

let x = 5;

let y = x++ * 2;  // y = 10, because x++ returns 5, then x becomes 6

!true && false    // false. ! runs first: (!true) && false → false && false

true || false && false  // true. && before ||: true || (false && false) → true || false


a = b = 5         // Assignment is right-to-left: a = (b = 5)

*When in doubt, use parentheses `()`*. They always win and make intent clear:

2 + 3 * 4        // works, but 

2 + (3 * 4)      // is clearer

if (age >= 18 && hasID || isVIP)  // confusing

if ((age >= 18 && hasID) || isVIP)  // explicit

*Rule of thumb*: `()` > math > compare > logic > assign. But just use parentheses instead of memorizing the full table.

## 🔎Section B – Output Prediction

### __11. Predict the output of the following program:__
### let a = 10;

### let b = 3;

### console.log(a + b);

### console.log(a - b);

### console.log(a * b);

### console.log(a / b);

### console.log(a % b);

Answer:
*Output:*
13

7

30

3.3333333333333335

1

*Why:*

1. `a + b` → `10 + 3` = `13`

2. `a - b` → `10 - 3` = `7` 

3. `a _ b` → `10 _ 3` = `30`

4. `a / b` → `10 / 3` = `3.3333333333333335` — JS uses floating-point division, not integer division

5. `a % b` → `10 % 3` = `1` — 3 goes into 10 three times with remainder 1
### __12. Predict the output of the following program:__
### let x = 5;

### console.log(x++);

### console.log(x);

answer:

*Output:*
5

6

*Why:*  

`x++` is post-increment. It returns the current value first, then adds 1.

1. `console.log(x++)` → prints `5`, then `x` becomes `6`

2. `console.log(x)` → prints `6`
### __13. Predict the output of the following program:

### let x = 5;

### console.log(++x);

### console.log(x);

Answer:

*Output:*
6

6
*Why:*  

`++x` is pre-increment. It adds 1 first, then returns the new value.

1. `console.log(++x)` → `x` becomes `6`, then prints `6`

2. `console.log(x)` → prints `6`
###  __14. Predict the output of the following program:__

### console.log(10 == "10");

### console.log(10 === "10");

Answer:

*Output:*

true

false

*Why:*

1. `10 == "10"` → `true`  

   `==` is loose equality. It converts the string `"10"` to number `10`, then compares `10 == 10`.

2. `10 === "10"` → `false`  

   `===` is strict equality. No type conversion. Number vs string, so different types = `false`.
### __15. Predict the output of the following program:__

### console.log(true && false);

### console.log(true || false);

### console.log(!true);

Answer:

*Output:*
false
true
false
*Why:*

1. `true && false` → `false`  
   `&&` AND needs both sides true. One is false, so result is `false`.

2. `true || false` → `true`  
   `||` OR needs at least one side true. First side is true, so result is `true`.

3. `!true` → `false`  
   `!` NOT flips the value. Not true is `false`.
### __16. Predict the output of the following program:__
### let a = 8;

### a += 2;
### a *= 3;

### __16. Predict the output of the following program:__
### let a = 8;

### a += 2;
### a *= 3;

### console.log(a);
### console.log(a);

Answer:
*Output:*

30

*Why:*

1. `a = 8`
2. `a += 2` → `a = a + 2` → `a = 8 + 2` → `a = 10`

3. `a _= 3` → `a = a _ 3` → `a = 10 * 3` → `a = 30`

Final `console.log(a)` prints `30`.

### __17. Predict the output of the following program:__
### console.log(5 > 3 && 10 < 20);
### console.log(5 > 10 || 8 == 8);

Answer:
*Output:*

true

true

*Why:*

1. `5 > 3 && 10 < 20`  
   `5 > 3` → `true`  
   `10 < 20` → `true`  
   `true && true` → `true`

2. `5 > 10 || 8 == 8`  
   `5 > 10` → `false`  
   `8 == 8` → `true`  
   `false || true` → `true`
### __18. Predict the output of the following program:__

### console.log(10 + "5");

### console.log("10" - 5);

Answer:

*Output:*

105

5

*Why:*

1. `10 + "5"` → `"105"`  
   When `+` has a string on either side, JS does concatenation. So `10` becomes `"10"` and `"10" + "5"` = `"105"`.

2. `"10" - 5` → `5`  
   `-` only does numeric subtraction. JS coerces `"10"` to `10`, then `10 - 5` = `5`.

*Gotcha*: `+` is special. It concatenates if any operand is a string. All other math operators force numbers.
## 🔎Section C – Write Programs

### __19. Write a program to add two numbers and display the result__

Here are 2 common ways to do it in JS:

*1. With fixed values:*
let num1 = 7;

let num2 = 12;

let sum = num1 + num2;

console.log("The sum is:", sum);  // The sum is: 19

*2. With user input in browser:*

let num1 = Number(prompt("Enter first number:"));

let num2 = Number(prompt("Enter second number:"));

let sum = num1 + num2;

console.log("The sum is:", sum);

alert("The sum is: " + sum);

Note: `prompt()` returns a string, so wrap it in `Number()` or you'd get concatenation instead of addition. `"5" + "3"` = `"53"`.

### __20. Write a program to calculate the area of a rectangle using operators.__
### Hint: a = l * b  Area(a) = Length(l) * Breadth(b)

*Using fixed values:*

let length = 10;

let breadth = 5;

let area = length * breadth;

console.log("Area of rectangle:", area);  // Area of rectangle: 50

*With user input in browser:*

let length = Number(prompt("Enter length:"));

let breadth = Number(prompt("Enter breadth:"));


let area = length * breadth;

console.log("Area = Length * Breadth");

console.log("Area =", area);

alert("Area of rectangle: " + area);

*As a reusable function:*

function rectangleArea(l, b) {

  return l * b;
}

console.log(rectangleArea(8, 4));  // 32

Remember: `_` is the multiplication operator in JS, so `a = l _ b` translates directly.
### __21. Write a program to swap two numbers using a third variable.__

let a = 5;

let b = 10;

console.log("Before swap: a =", a, "b =", b);


let temp = a;  // store a in temp

a = b;         // put b into a  

b = temp;      // put temp (original a) into b


console.log("After swap: a =", a, "b =", b);

Output:

Before swap: a = 5 b = 10

After swap: a = 10 b = 5
### __22. Write a program to swap two numbers without using a third variable..__

*Method 1: Using arithmetic*

let a = 5;

let b = 10;

console.log("Before swap: a =", a, "b =", b);

a = a + b;  // a = 15

b = a - b;  // b = 15 - 10 = 5

a = a - b;  // a = 15 - 5 = 10

console.log("After swap: a =", a, "b =", b);

*Method 2: Using destructuring - cleanest way in JS*

let a = 5;

let b = 10;

console.log("Before swap: a =", a, "b =", b);

[a, b] = [b, a];

console.log("After swap: a =", a, "b =", b);

*Output for both:*

Before swap: a = 5 b = 10

After swap: a = 10 b = 5

Destructuring is the modern JS way. The arithmetic method can have overflow issues with very large numbers.

### __23. Write a program to calculate annual interest.__
### I = (PRT)/100
### I = annual interest
### P = principal amount
### R = rate
### T = time period(duration)

Answer:

*Using fixed values:*

let P = 10000;  // principal amount

let R = 5;      // rate of interest per year in %

let T = 3;      // time period in years

let I = (P * R * T) / 100;

console.log("Principal:", P);

console.log("Rate:", R + "%");

console.log("Time:", T, "years");

console.log("Annual Interest:", I);  // Annual Interest: 1500

*With user input in browser:*

let P = Number(prompt("Enter Principal amount:"));

let R = Number(prompt("Enter Rate of interest (%):"));

let T = Number(prompt("Enter Time period in years:"));

let I = (P * R * T) / 100;

console.log("I = (P * R * T) / 100");

console.log("I =", I);

alert("Annual Interest: " + I);

*As a function:*

function calculateInterest(principal, rate, time) {

  return (principal * rate * time) / 100;
}

console.log(calculateInterest(20000, 7.5, 2));  // 3000

Formula `I = (PRT)/100` translates directly to JS using `*` for multiplication and `/` for division.
### __24. Write a program to convert Fahrenheit to Celsius.__
### C = ((F -32) * 5) / 9
Answer:

*Using a fixed value:*

let F = 98.6;  // Fahrenheit

let C = ((F - 32) * 5) / 9;

console.log(F + "°F =", C.toFixed(2) + "°C");  // 98.6°F = 37.00°C

`.toFixed(2)` rounds to 2 decimal places for cleaner output.

*With user input in browser:*

let F = Number(prompt("Enter temperature in Fahrenheit:"));

let C = ((F - 32) * 5) / 9;

console.log("C = ((F - 32) * 5) / 9");

console.log(F + "°F =", C + "°C");

alert(F + "°F = " + C.toFixed(2) + "°C");

*As a function:*

function fahrenheitToCelsius(f) {

  return ((f - 32) * 5) / 9;
}

console.log(fahrenheitToCelsius(32));   // 0

console.log(fahrenheitToCelsius(212));  // 100

Formula maps directly: parentheses handle the order `F - 32` first, then `* 5`, then `/ 9`.

### __25. Create a BMI calculator.__
### BMI = Weight(kg) / (height(m) * height(m))

*Basic BMI calculation:*

let weight = 70;    // kg

let height = 1.75;  // meters

let bmi = weight / (height * height);

console.log("BMI:", bmi.toFixed(2));  // BMI: 22.86

*With user input + BMI category:*

let weight = Number(prompt("Enter weight in kg:"));

let height = Number(prompt("Enter height in meters:"));

let bmi = weight / (height * height);
let category = "";


if (bmi < 18.5) {

  category = "Underweight";

} else if (bmi < 25) {

  category = "Normal weight";

} else if (bmi < 30) {

  category = "Overweight";

} else {

  category = "Obese";
}

console.log("Your BMI is:", bmi.toFixed(1));

console.log("Category:", category);

alert("BMI: " + bmi.toFixed(1) + " - " + category);

*As a reusable function:*

function calculateBMI(weightKg, heightM) {

  return weightKg / (heightM * heightM);
}

console.log(calculateBMI(65, 1.70));  // 22.49

*BMI Categories:*

- *Under 18.5*: Underweight

- *18.5-24.9*: Normal weight  

- *25-29.9*: Overweight

- *30+*: Obese

Formula `BMI = weight / (height _ height)` uses `/` for division and `_` for multiplication. Use meters, not cm.
### __26. Create a discount percentage calculator.__
### discountPercentage = ((MRP – sellingPrice) * 100) / MRP

*Basic calculation:*

let MRP = 1000;           // Maximum Retail Price

let sellingPrice = 750;   // Price after discount

let discountPercentage = ((MRP - sellingPrice) * 100) / MRP;

console.log("MRP: $" + MRP);

console.log("Selling Price: $" + sellingPrice);

console.log("Discount:", discountPercentage.toFixed(2) + "%");  // Discount: 25.00%

*With user input:*

let MRP = Number(prompt("Enter MRP:"));

let sellingPrice = Number(prompt("Enter Selling Price:"));

let discount = MRP - sellingPrice;

let discountPercentage = (discount * 100) / MRP;


console.log("Discount Amount: $" + discount);

console.log("Discount Percentage: " + discountPercentage.toFixed(2) + "%");

alert("You save " + discountPercentage.toFixed(1) + "%");

*As a function:*

function getDiscountPercent(mrp, sellingPrice)

 {

  return ((mrp - sellingPrice) * 100) / mrp;
  
 }

console.log(getDiscountPercent(2000, 1600));  // 20

console.log(getDiscountPercent(50, 40));      // 20

*How it works*: First find the discount amount `MRP - sellingPrice`, then convert to percentage by `* 100 / MRP`.
## 🔎Section E – Advanced / Conceptual Questions

### __27. Explain type coercion in JavaScript with examples.__

*Type coercion* is when JavaScript automatically converts a value from one type to another during operations. It happens because JS is "weakly typed".

There are 2 kinds: implicit and explicit.

*1. Implicit coercion - JS does it automatically*

JS decides based on the operator:

*String coercion with `+`:*

console.log(5 + "5");        // "55"

console.log("Age: " + 25);   // "Age: 25"

console.log(true + "1");     // "true1"

If either side of `+` is a string, JS converts the other to string and concatenates.

*Number coercion with `-`, `*`, `/`:*

console.log("10" - 5);       // 5

console.log("6" * "2");      // 12  

console.log("20" / 4);       // 5

console.log("hello" - 5);    // NaN

Math operators force numbers. If it can't convert, you get `NaN`.

*Boolean coercion in conditionals:*

if ("hello") { console.log("runs"); }  // runs

if (0) { console.log("skips"); }       // skips

if ([]) { console.log("runs"); }       // runs - empty array is truthy

Values convert to `true` or `false`. Falsy values: `0`, `""`, `null`, `undefined`, `NaN`, `false`.

*Loose equality `==`:*

console.log(5 == "5");       // true - string "5" becomes number 5

console.log(0 == false);    // true - both become 0

console.log(null == undefined); // true - special case

console.log([] == 0);       // true - [] becomes "" becomes 0

*2. Explicit coercion - you convert it yourself*
Number("42");     // 42

String(100);      // "100"

Boolean(1);       // true

parseInt("15px"); // 15

*Gotchas to watch:*

1. `+` is overloaded: `1 + 2 + "3"` = `"33"`, not `"123"`. Left to right: `1+2=3`, then `3+"3"="33"`.

2. `==` is weird: use `===` to avoid coercion. `5 === "5"` is `false`.

3. `null` and `undefined`: `null + 1` = `1`, but `undefined + 1` = `NaN`.

*Rule of thumb*: Coercion with `+` favors strings. All other math operators favor numbers. When in doubt, convert explicitly or use `===`.

### __28. Why does "5" + 2 produce a different result from "5" - 2?__

It's all about how JS handles `+` vs other math operators.

*`"5" + 2` gives `"52"`*  

The `+` operator does string concatenation if either side is a string. JS converts `2` to `"2"`, then joins: `"5" + "2"` = `"52"`

"5" + 2  // "52"  - type is string

*`"5" - 2` gives `3`*  

The `-` operator only does arithmetic. It forces both values to numbers first. JS converts `"5"` to `5`, then subtracts: `5 - 2` = `3`

"5" - 2  // 3  - type is number

*Rule*:  

- `+` with a string = concatenation

- `-`, `*`, `/` = always numeric coercion

Same thing happens with `"10" + 5` → `"105"` vs `"10" - 5` → `5`. 

This is why `===` is safer than `==`, and why we used `Number()` in the earlier programs to avoid this trap.
### __29. What is short-circuit evaluation in logical operators?__

*Short-circuit evaluation* means JS stops evaluating a logical expression as soon as the result is determined. It doesn't bother checking the rest.

This works because `&&` and `||` don't just return `true`/`false` - they return one of the actual operands.

### `&&` - AND operator

Stops and returns the first falsy value it finds. If all are truthy, returns the last value.

false && console.log("won't run");  // stops at false, never runs console.log

true && "hello" && 42  // returns 42 - all truthy, so last value

let name = "" && "default";  // name = ""  because "" is falsy

Common use: guard against null before accessing properties

user && user.name  // if user is null/undefined, stops and returns it. No error.

### `||` - OR operator  

Stops and returns the first truthy value it finds. If all are falsy, returns the last value.

true || console.log("won't run");   // stops at true, never runs console.log

false || 0 || "yes" || 100  // returns "yes" - first truthy value

let name = userInput || "Guest";  // fallback if userInput is empty/falsy

### `??` - Nullish coalescing 

Only short-circuits on `null` or `undefined`, not other falsy values like `0` or `""`.

0 || 100     // 100  because 0 is falsy

0 ?? 100     // 0    because 0 is not null/undefined

let count = input ?? 0;  // only uses 0 if input is null/undefined

*Why it matters*: 

1. Performance - skips unnecessary work

2. Avoid errors - `obj && obj.prop` won't crash if `obj` is null

3. Set defaults - `value || default`

*Falsy values in JS*: `false`, `0`, `""`, `null`, `undefined`, `NaN`. Everything else is truthy, including `[]` and `{}`.
### __30. Predict the output of the following program:__
### console.log(true + true);
### console.log(false + 1);

*Output:*

2

1

*Why:*

In JS, boolean values get coerced to numbers during arithmetic.

- `true` → `1`
- `false` → `0`

So:

console.log(true + true);   // 1 + 1 = 2

console.log(false + 1);     // 0 + 1 = 1

This only happens with math operators like `+`, `-`, `*`, `/`. If you did `true + "1"` you'd get `"true1"` because `+` with a string does concatenation instead.
### __31. Explain truthy and falsy values in JavaScript.__

*Falsy values* are values that convert to `false` when checked in a boolean context like an `if` statement. 

*Truthy values* are everything else - they convert to `true`.

### __The 7 falsy values in JS__

These are the only falsy ones. Memorize them:

1. `false`

2. `0` and `-0`

3. `""` - empty string

4. `null`

5. `undefined`

6. `NaN`

7. `0n` - BigInt zero

if (0) console.log("won't run");

if ("") console.log("won't run");

if (null) console.log("won't run");

### __Truthy values__

Literally everything that's not falsy:

if ("hello") console.log("runs");     // non-empty string

if (42) console.log("runs");          // non-zero number

if ([]) console.log("runs");          // empty array

if ({}) console.log("runs");          // empty object

if ("0") console.log("runs");         // string "0" is truthy

if ("false") console.log("runs");     // non-empty string

*Gotchas:*

1. Empty arrays/objects are truthy: `[]` and `{}` → `true`

2. String `"0"` and `"false"` are truthy, only `""` is falsy

3. `typeof null` is `"object"` but `null` is still falsy

### Where this matters:

Used in conditionals and with `||`, `&&`, `!`

let name = input || "Guest";        // fallback if input is falsy

user && user.login();               // only run if user is truthy

if (!arr.length) console.log("empty"); // 0 is falsy, so !0 is true

Check truthiness: `Boolean(value)` or `!!value`

Boolean("hello");  // true

!!0;              // false


