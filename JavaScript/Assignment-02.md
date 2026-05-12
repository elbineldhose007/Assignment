# __📂02.JAVASCRIPT Assignment💻__

## Section A: Basic Questions

## __1. What are data types in JavaScript?__
### JavaScript has *8 data types:

7 Primitive types* – single, immutable values:
1. *String* – text: `"hello"`
2. *Number* – integers/decimals: `42`, `3.14`
3. *BigInt* – large integers: `123n`
4. *Boolean* – `true` / `false`
5. *Undefined* – variable declared, no value
6. *Null* – intentional empty value
7. *Symbol* – unique identifier: `Symbol()`

*1 Non-primitive type*:
8. *Object* – collections of data: `{key: "value"}`, arrays `[1,2]`, functions are also objects.

## __2. List all primitive data types in JavaScript.__

All Primitive Data Types in JavaScript – 7 total

1. *String* – Text data  
   Ex: `"Hello"`, `'JS'`, `` `template` ``

2. *Number* – Integers & floating point  
   Ex: `10`, `3.14`, `-5`, `NaN`, `Infinity`

3. *BigInt* – Large integers beyond `Number` limit  
   Ex: `123456789012345678901234567890n`

4. *Boolean* – Logical value  
   Ex: `true`, `false`

5. *Undefined* – Variable declared but not assigned  
   Ex: `let x;` → `x` is `undefined`

6. *Null* – Intentional absence of any value  
   Ex: `let y = null`

7. *Symbol* – Unique, immutable identifier  
   Ex: `Symbol("id")`, `Symbol()`
## __3. What is the difference between primitive and non-primitive data types?__

Primitive types: Store a single value directly. They are _immutable_ and _copied by value_.  
Ex: `String`, `Number`, `Boolean`, `null`, `undefined`, `Symbol`, `BigInt`

Non-Primitive types: Store collections or complex data. They are _mutable_ and _copied by reference_.  
Ex: `Object`, `Array`, `Function`

*Key difference*:  
Primitives hold the _actual value_ in memory. Non-primitives hold a _reference/address_ to the data in memory.

*Example*:  
`let a = 5; let b = a;` → `b` gets a separate copy.  
`let obj1 = {x:5}; let obj2 = obj1;` → both point to the same object.

## __4. What is the `typeof` operator? Give examples.__

`typeof` is a JavaScript operator that _returns the data type_ of a value as a string.

*Syntax*: `typeof value` or `typeof(value)`

*Examples:*
typeof "hello"      // "string"
typeof 42           // "number" 
typeof true         // "boolean"
typeof undefined    // "undefined"
typeof {a: 1}       // "object"
typeof [1, 2]       // "object" 
typeof function(){} // "function"
typeof null         // "object"  ← known JS bug

## __5. What is the `undefined` data type?__

`undefined` is a primitive data type in JavaScript.

*When it occurs:*
1. *Variable declared but not assigned*  
   let x; 
   console.log(x); // undefined
2. *Function has no return value*  
   function test() {}
   console.log(test()); // undefined
3. *Accessing non-existent object property*  
   let obj = {};
   console.log(obj.name); // undefined
*Key points:*
- It’s both a _type_ and a _value_.
- `typeof undefined` → `"undefined"`
- Different from `null` – `undefined` means “not assigned”, `null` means “intentionally empty”.

## __6. What is `null` in JavaScript?__

`null` is a primitive data type that represents _intentional absence of any value_.

*Key points:*
1. *Meaning*: You purposely set a variable to "empty" or "no value".
2. *Type*: `typeof null` → `"object"` – this is a famous JS bug, but `null` is actually a primitive.
3. *Difference from `undefined`*: `undefined` = not assigned yet. `null` = deliberately empty.

*Example:*
let user = null; // no user logged in yet
user = {name: "Arun"}; // later assigned

let x; 
console.log(x); // undefined – not assigned
console.log(user); // null – we set it empty on purpose

## __7. What is the difference between `null` and `undefined`?__

*`undefined`*: JS sets it automatically when a variable is declared but not given a value.  
Ex: `let x;` → `x` is `undefined`

*`null`*: You assign it manually to show "empty" or "no value" on purpose.  
Ex: `let y = null;` → you set it empty

*Key difference*: `undefined` = not assigned yet. `null` = intentionally empty.

`typeof undefined` → `"undefined"`  
`typeof null` → `"object"`

## __8. What is the `boolean` data type? Give examples.__

`Boolean` is a primitive data type in JavaScript that has only *two values*: `true` or `false`.

*Used for*: Logical operations, conditions, yes/no decisions.

*Examples:*
let isOnline = true;
let isLoggedIn = false;

console.log(5 > 3);      // true
console.log(10 === 5);   // false

if (isOnline) {
  console.log("User is online"); // runs because true
}
*Type check*: `typeof true` → `"boolean"`

*Falsy values*: `false`, `0`, `""`, `null`, `undefined`, `NaN` become `false` in conditions.  
Everything else is `truthy`.

## __9. What is a `string` in JavaScript?__

`String` is a primitive data type used to store _text_.

*How to create*: Use single quotes `' '`, double quotes `" "`, or backticks `` ` ``
let name = "Arun";
let city = 'Guruvayoor';
let msg = `Hello, ${name}`; // template literal
*Key points:*
1. *Immutable* – once created, you can’t change characters directly.
2. *Indexed* – `name[0]` → `"A"`
3. *Has properties/methods* – `name.length` → `4`, `name.toUpperCase()` → `"ARUN"`

*Type check*: `typeof "hello"` → `"string"`

*In short*: `String` = text data. Any characters inside quotes.

## __10. What is a `number` data type? Does JavaScript support integers and floats separately?__


`Number` is a primitive type in JavaScript for _numeric values_.

*Does JS have separate integers and floats?*  
*No.* JS has only _one_ `Number` type for both integers and floats. Both are stored as 64-bit floating point.

*Examples:*
let age = 25;        // integer
let price = 99.99;   // float
let temp = -5;       // negative
let inf = Infinity;  // special number
let notNum = NaN;    // "Not a Number"

typeof 10     // "number"
typeof 3.14   // "number" 
*Note*: For very large integers, use `BigInt` → `123n`

*In short*: JS `Number` covers both integers and decimals. No separate `int` or `float` type.

## Section B: Conceptual Questions

## __11. What is the `symbol` data type in JavaScript?__

`Symbol` is a primitive data type introduced in ES6. It creates _unique and immutable_ values.

*Key point*: Every `Symbol()` is always different, even if the description is same.

*Syntax*: `Symbol(description)`

*Example:*
let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2); // false – always unique
*Main use*: Add unique property keys to objects so they don’t clash.
const user = {};
let userId = Symbol("id");
user[userId] = 101;
*Type check*: `typeof Symbol()` → `"symbol"`

## __12. What is `bigint` and why is it used?__

`BigInt` is a primitive data type for _very large integers_ that `Number` can’t safely store.

*Why used*: `Number` in JS is 64-bit float and loses precision beyond `2^53 - 1` → `9007199254740991`.  
`BigInt` handles numbers bigger than that.

*How to create*: Add `n` at the end, or use `BigInt()`
let big = 9007199254740993n; 
let big2 = BigInt(9007199254740993);

typeof big  // "bigint"
*Rules*: 
1. Can't mix with `Number` → `10n + 5` gives error. Do `10n + 5n`.
2. No decimals → `10n / 3n` → `3n`

*Use case*: Cryptography, large IDs, financial calculations needing exact integers.

## __13. What happens when you use `typeof null`?__

typeof null  // "object"
*What happens*: It returns `"object"`, not `"null"`.

*Why*: This is a famous bug in JavaScript from version 1. In the original JS, values were stored as type tags. `null` was represented as all zeros, same as object tag. So `typeof null` became `"object"`.

*Note*: Even though it says `"object"`, `null` is actually a _primitive_, not an object.

*How to check for null correctly:*
let x = null;
console.log(x === null); // true – use this instead

## __14. Explain type coercion with examples.__
Type coercion is when JavaScript _automatically converts_ one data type to another.

*Two types:*
1. *Implicit* – JS does it automatically 
2. *Explicit* – You do it on purpose

*Implicit Examples:*
"5" + 2       // "52" → number 2 becomes string, + does concat
"5" - 2       // 3    → string "5" becomes number, - does math
true + 1      // 2    → true becomes 1
null + 1      // 1    → null becomes 0
undefined + 1 // NaN  → undefined becomes NaN

if ("hello") { } // "hello" becomes true
if (0) { }       // 0 becomes false
*Explicit Examples:*
Number("5")   // 5
String(10)    // "10"
Boolean(0)    // false
*Key rule*: `+` with string does concat. Other math operators `- * /` force numbers.

*In short*: Coercion = JS auto-converting types. Can cause bugs, so use `===` to avoid it.

## __15. What is implicit and explicit type conversion?__

*1. Implicit Conversion / Coercion*  
JavaScript converts types _automatically_ behind the scenes.
"5" + 3        // "53"  → 3 becomes string because of +
"10" - 2       // 8     → "10" becomes number because of -
if ("hello")   // true  → string becomes boolean
true + 1       // 2     → true becomes 1
*Happens with*: `+` if one operand is string, math operators `- * /`, `==`, `if()` conditions.

*2. Explicit Conversion / Type Casting*  
You manually convert types using functions.
Number("5")    // 5
String(100)    // "100"
Boolean(0)     // false
parseInt("5.9")  // 5
parseFloat("3.14") // 3.14
*In short*:  
*Implicit* = JS does it auto, can be tricky.  
*Explicit* = You do it with `Number()`, `String()`, `Boolean()`. More predictable.

## __16. What is `NaN`? When does it occur?__

`NaN` = "Not-a-Number". It's a special `Number` type value that means _invalid number result_.

*When it occurs:*
0 / 0                  // NaN
"hello" * 5            // NaN – can't multiply text
Number("abc")          // NaN – can't convert to number
Math.sqrt(-1)          // NaN – invalid math
undefined + 1          // NaN
parseInt("text")       // NaN
*Key weirdness:*
typeof NaN     // "number" – yes, it's still Number type
NaN === NaN    // false – NaN is never equal to itself
*How to check:*
isNaN("hello")        // true 
Number.isNaN(NaN)     // true – safer, no coercion
`NaN` = result of invalid math or failed number conversion. Check with `Number.isNaN()`.

## Section C: Practical / Coding Questions

### __17. Write a program to check the data type of a variable.__

let data = 42;
console.log(typeof data);  // number

data = "hello";
console.log(typeof data);  // string

data = true;
console.log(typeof data);  // boolean

data = [1, 2, 3];
console.log(typeof data);  // object

data = null;
console.log(typeof data);  // object – quirk in JS

### __18. Declare variables of all primitive data types and print their types.__

let str = "hello";           // string

let num = 42;                // number

let big = 9007199254740991n; // bigint

let bool = true;             // boolean

let und = undefined;         // undefined

let nul = null;              // null

let sym = Symbol("id");      // symbol

console.log(typeof str);   // string

console.log(typeof num);   // number

console.log(typeof big);   // bigint

console.log(typeof bool);  // boolean

console.log(typeof und);   // undefined

console.log(typeof nul);   // object – known JS quirk

console.log(typeof sym);   // symbol


### __19. Write a program to convert a string to a number.__

*3 common ways to convert string → number:*

let str = "42";

// 1. Number()

let num1 = Number(str);

console.log(num1, typeof num1);  // 42 number

// 2. parseInt() for integers

let num2 = parseInt(str);

console.log(num2, typeof num2);  // 42 number

// 3. Unary + operator

let num3 = +str;

console.log(num3, typeof num3);  // 42 number

*For decimals:*

let price = "19.99";

console.log(parseFloat(price));  // 19.99

console.log(Number(price));      // 19.99

*Note*: If string isn't a valid number, `Number("abc")` gives `NaN`. `parseInt("42px")` gives `42`.
 
### __20. Write a program to convert a number to a string.__

*3 ways to convert number → string:*
let num = 42;

// 1. String()
let str1 = String(num);
console.log(str1, typeof str1);  // "42" string

// 2. toString()
let str2 = num.toString();
console.log(str2, typeof str2);  // "42" string

// 3. Template literal or concatenation
let str3 = `${num}`;
let str4 = num + "";
console.log(str3, typeof str3);  // "42" string
*Note*: `toString()` won't work on `null` or `undefined`, but `String()` handles those. `String(null)` gives `"null"`.

### __21. What will be the output of:__
### console.log(typeof 42);

### console.log(typeof "Hello");

### console.log(typeof true);

### console.log(typeof undefined);

### console.log(typeof null);

Answer:


console.log(typeof 42);         // "number"

console.log(typeof "Hello");    // "string"

console.log(typeof true);       // "boolean"

console.log(typeof undefined);  // "undefined"

console.log(typeof null);       // "object"


### __22. Predict the output:__
### console.log(5 + "5");
### console.log("5" - 2);
### console.log(true + 1);
### console.log(false + "hello");

Answer:

*Output:*
console.log(5 + "5");        // "55"

console.log("5" - 2);        // 3

console.log(true + 1);       // 2

console.log(false + "hello"); // "falsehello"

*Why:*

1. `5 + "5"` → `+` with a string does concatenation: number becomes `"5"`, so `"55"`

2. `"5" - 2` → `-` only works with numbers, so `"5"` coerces to `5`, giving `3`

3. `true + 1` → `true` coerces to `1`, so `1 + 1 = 2`

4. `false + "hello"` → `+` with a string does concatenation: `false` becomes `"false"`, so `"falsehello"`

### __23. Create an object and an array, then check their data types using `typeof`.__

*Code:*
let user = { id: 1, name: "Elbin" };

let scores = [90, 85, 100];

console.log(typeof user);    // object

console.log(typeof scores);  // object

*Key point*: In JS, arrays are actually objects, so `typeof` gives `"object"` for both.


Use `Array.isArray(scores)` if you need to specifically detect arrays. That returns `true` for arrays, `false` for plain objects.

## Section D: Advanced Thinking

### __24. Can a variable change its data type? Explain with example.__

*Yes*. JavaScript is dynamically typed, so a variable can hold different types at different times.

*Example:*
let data = 42;

console.log(typeof data);  // number

data = "now I'm text";

console.log(typeof data);  // string

data = true;

console.log(typeof data);  // boolean

data = { id: 1 };

console.log(typeof data);  // object

*Explanation*: The variable `data` isn't locked to one type. When you assign a new value, JS just changes what type the variable holds. 

This is different from statically typed languages like Java or C++ where `int x = 5;` means `x` can only ever be an integer.

### __25. How does JavaScript handle large integers?__

*Two ways:*

*1. `number` type*  
JS uses 64-bit floating point. Integers are safe up to `Number.MAX_SAFE_INTEGER`:

console.log(Number.MAX_SAFE_INTEGER);  // 9007199254740991

console.log(9007199254740991 + 1);     // 9007199254740992

console.log(9007199254740991 + 2);     // 9007199254740992 – wrong

Above that, precision breaks and you get rounding errors.


*2. `bigint` type*  

For arbitrarily large integers, use `bigint`. Add `n` to the end or use `BigInt()`:

let big = 9007199254740991n;

console.log(big + 2n);  // 9007199254740993n – correct

let huge = BigInt("123456789012345678901234567890");

console.log(huge);  // 123456789012345678901234567890n

*Rules*: You can't mix `bigint` and `number` in operations: `10n + 5` throws an error. Use `10n + 5n` instead.