# __📁JAVASCRIPT Assigment-String Methods()💻__
## Part A: Basic Questions
### 1. What is a string in JavaScript?
A string in JavaScript is data used to represent text.It's a sequence of characters like letters, numbers, symbols, or spaces, wrapped in quotes.
### 2. How do you create a string using double quotes, single quotes, and backticks?
Double Quotes "
```
let name = "Cricket";
let msg = "He said \"Hello\""; // Use \ to escape quotes inside
console.log(name); // Cricket
```
 Single quotes '
```
let game = 'Football';
let quote = 'It\'s a good day'; // Use \ to escape ' inside
console.log(game); // Football
```
Backticks ` - template literals
```
let sport = `Tennis`;
let player = "Virat";
let score = 100;

// Can do variable interpolation with ${}
let message = `${player} scored ${score} in ${sport}`;
console.log(message); // Virat scored 100 in Tennis

// Can write multi-line strings without \n
let poem = `Roses are red
Violets are blue`;
```
### 3. What is the difference between length and trim()?
*`length` and `trim()` do completely different things.*

*`length` - Property that counts characters*
let word = "  Hello  ";

console.log(word.length); // 9

It counts _every_ character: letters, spaces, tabs, punctuation. No changes to the string.

*`trim()` - Method that removes whitespace from start/end*

let word = "  Hello  ";

console.log(word.trim()); // "Hello"

console.log(word.trim().length); // 5

It deletes spaces, tabs, and newlines only at the beginning and end. Middle spaces stay.


console.log(userInput.length); // 10 - original still has spaces

console.log(clean.length); // 5 - new string is trimmed

Use `length` to measure. Use `trim()` to clean up user input before checking it.
### 4. What does toUpperCase() do?
*`toUpperCase()` converts all letters in a string to capital letters.*

It returns a _new_ string. The original string stays unchanged because strings are immutable.

*Basic usage:*

let name = "cricket";

let bigName = name.toUpperCase();

console.log(bigName); // "CRICKET"

console.log(name);    // "cricket" - original didn't change


*Key points:*
1. *Only affects letters*: Numbers, symbols, spaces stay the same

   "hello123!".toUpperCase(); // "HELLO123!"


2. *Returns new string*: You have to store it if you want to use it

   let game = "footBall";

   game.toUpperCase(); // This does nothing by itself

   console.log(game);  // Still "footBall"
   
   game = game.toUpperCase(); // Now it works

   console.log(game);  // "FOOTBALL"



3. *Common use*: Case-insensitive comparisons

   let userInput = "Yes";

   if (userInput.toUpperCase() === "YES") {

     console.log("User agreed"); // This runs

   }


There's also `toLowerCase()` which does the opposite: `"HELLO".toLowerCase()` → `"hello"`
### 5. What does toLowerCase() do?
*`toLowerCase()` converts all letters in a string to small letters.*

It returns a _new_ string. The original stays unchanged because strings are immutable.

*Basic usage:*

let name = "CRICKET";

let smallName = name.toLowerCase();

console.log(smallName); // "cricket"

console.log(name);      // "CRICKET" - original didn't change


*Key points:*

1. *Only affects letters*: Numbers, symbols, spaces stay the same

   "HELLO123!".toLowerCase(); // "hello123!"



2. *Returns new string*: You must store it to use it

   let game = "FootBall";

   game.toLowerCase(); // Does nothing by itself

   console.log(game);  // Still "FootBall"

   
   game = game.toLowerCase(); // Now it works

   console.log(game);  // "football"


3. *Common use*: Case-insensitive comparisons

   let userInput = "Yes";

   if (userInput.toLowerCase() === "yes") {

     console.log("User agreed"); // This runs
   }


*Pair with `toUpperCase()`*: `"hello".toUpperCase()` → `"HELLO"` and `"HELLO".toLowerCase()` → `"hello"`
### 6. What is the use of includes()?
*`includes()` checks if a string contains another substring. Returns `true` or `false`.*

*Syntax:* `string.includes(substring)`

*Basic examples:*

let sentence = "I love Cricket";

console.log(sentence.includes("Cricket")); // true

console.log(sentence.includes("cricket")); // false - it's case sensitive

console.log(sentence.includes("love"));    // true

console.log(sentence.includes("z"));       // false


*Key details:*

1. *Case sensitive*: `"Hello".includes("h")` → `false`

   let text = "JavaScript";

   text.includes("Script"); // true

   text.includes("script"); // false


2. *Returns boolean only*: No index, just yes/no

   let email = "user@gmail.com";

   if (email.includes("@")) {

     console.log("Valid email format"); // This runs
   }


3. *Optional start position*: `string.includes(substring, startIndex)
`
   "Blueberry".includes("blue", 0); // false - B vs b

   "Blueberry".includes("berry", 4); // true - starts checking at index 4



*Common uses:*

- Validating input: `password.includes("123")`

- Filtering: `if (filename.includes(".jpg"))`


- Searching text: `comment.includes("spam")`

*Note*: For arrays it works too: `[1,2,3].includes(2)` → `true`. But for strings, it's the go-to way 
to check "does this text contain that piece of text?"
### 7. What is the difference between slice() and substring()?
*Both `slice()` and `substring()` extract part of a string. The difference is how they handle negative indexes and swapped arguments.*

*Syntax:* `string.slice(start, end)` vs `string.substring(start, end)`

Both cut from `start` up to, but not including, `end`.

*Examples:*

*1. Normal use - they work the same*

let word = "Cricket";

word.slice(1, 4);     // "ric"

word.substring(1, 4); // "ric"


*2. Negative indexes*

let word = "Cricket"; // length 7

word.slice(-3);       // "ket" - last 3 chars

word.substring(-3);   // "Cricket" - negative becomes 0

word.slice(1, -2);    // "rick" - from index 1 to length-2

word.substring(1, -2); // "C" - -2 becomes 0, then swaps to (0,1)


*3. start > end*

let word = "Cricket";

word.slice(4, 1);     // "" - empty, because 4 > 1

word.substring(4, 1); // "ric" - swaps to (1, 4)


*Rule of thumb:*

- Use `slice()` if you need negative indexes to count from the end. Most common.

- Use `substring()` if you want it to auto-fix when start > end.

Both leave the original string unchanged because strings are immutable.
### 8. What does replace() do?
*`replace()` finds a piece of text and swaps it with something else. Returns a new string.*

*Syntax:* `string.replace(searchValue, newValue)`

*Key thing:* By default it only replaces the _first match_. Original string stays unchanged.

*Basic examples:*

let msg = "I like football. Football is great.";

let newMsg = msg.replace("football", "cricket");

console.log(newMsg); // "I like cricket. Football is great."

console.log(msg);    // "I like football. Football is great." - original unchanged

*Important details:*

1. *Only first match gets replaced*

   "ha ha ha".replace("ha", "he"); // "he ha ha"

2. *Case sensitive*

   "Hello hello".replace("hello", "hi"); // "Hello hi" - Hello with capital H wasn't touched

3. *To replace ALL matches, use regex with `g` flag*

   "ha ha ha".replace(/ha/g, "he"); // "he he he"

   Or newer method: `"ha ha ha".replaceAll("ha", "he")` → `"he he he"`

4. *Works with variables*

   let text = "User: John";

   let name = "Virat";

   let updated = text.replace("John", name); // "User: Virat"

*Common use*: Cleaning data, formatting, censoring words.

let phone = "123-456-7890";

let clean = phone.replace(/-/g, ""); // "1234567890"

Note: `replace()` doesn't mutate the original string. You must store the result.
### 9. What is the purpose of split()?
*`split()` breaks a string into an array of smaller strings, using a separator you choose.*

*Syntax:* `string.split(separator)`

It does the opposite of `join()`. Original string stays unchanged.

*Basic examples:*

let csv = "red,green,blue";

let colors = csv.split(",");

console.log(colors); // ["red", "green", "blue"]

let sentence = "I love JS";

let words = sentence.split(" ");

console.log(words); // ["I", "love", "JS"]


*Key details:*

1. *Separator is removed* from the result

   "a-b-c".split("-"); // ["a", "b", "c"] - the "-" is gone


2. *Split by each character* with empty string `""`

   "hello".split(""); // ["h", "e", "l", "l", "o"]


3. *No separator* gives you array with the whole string

   "hello".split(); // ["hello"]


4. *Optional limit*: `split(separator, limit)`

   "a,b,c,d".split(",", 2); // ["a", "b"] - only first 2 items


*Common uses:*
- Parse CSV: `"name,age,city".split(",")`

- Get words: `sentence.split(" ")`

- Reverse a string: `"cat".split("").reverse().join("")` → `"tac"`

*Note*: If separator isn't found, you get `["originalString"]`.
### 10. What is the difference between charAt() and bracket notation (str[0])?
*Both get a single character from a string. The main difference is what happens when the index doesn't exist.*

*Syntax:*

let str = "Cricket";

str.charAt(0); // "C"

str[0]; // "C"

*1. Normal use - same result*

let word = "Hello";

word.charAt(2); // "l"

word[2]; // "l"

*2. Index out of range*

let word = "Hi"; // length 2, indexes 0 and 1

word.charAt(5); // "" - empty string

word[5]; // undefined

This matters in `if` checks:

if (word.charAt(5)) { } // false, because "" is falsy

if (word[5]) { } // false, because undefined is falsy

// But if you check === "", only charAt works

*3. No argument*

let word = "JS";

word.charAt(); // "J" - defaults to index 0

word[]; // SyntaxError - invalid

*Which to use?*

Bracket notation `str[0]` is shorter and more common in modern JS. Use `charAt()` if you 
specifically need `""` instead of `undefined` for missing indexes, or if you're supporting very old browsers.

Both are read-only. You can't do `str[0] = "X"` because strings are immutable.
### 11. What does indexOf() return if the value is not found?
*`indexOf()` returns `-1` if the value is not found.*

*Why -1?* Because valid indexes start at `0`. So `-1` clearly means "not here".

*Examples:*
let text = "Cricket";

text.indexOf("C");   // 0 - found at start

text.indexOf("k");   // 3 - found at index 3

text.indexOf("z");   // -1 - not found

text.indexOf("ket"); // 4 - substring starts at index 4

text.indexOf("KET"); // -1 - case sensitive


*Common pattern for checking existence:*

let email = "user@gmail.com";

if (email.indexOf("@") === -1) {

  console.log("Invalid email"); // runs if @ is missing
}

// Or the inverse

if (email.indexOf("@") !== -1) {

  console.log("Has @ symbol");
}


*Note*: This applies to arrays too. `[1,2,3].indexOf(4)` → `-1`

For a cleaner check, modern JS also has `includes()`: `email.includes("@")` returns `true/false` instead of an index. But `indexOf()` is useful when you need the actual position, not just yes/no.
### 12. Explain the use of startsWith() and endsWith().
*`startsWith()` and `endsWith()` check if a string begins or ends with specific text. Both return `true` or `false`.*

They're simpler than `indexOf()` when you only care about the start or end.

*Syntax:*

string.startsWith(searchString)

string.endsWith(searchString)

*Examples:*

*1. `startsWith()`*

let filename = "report.pdf";

filename.startsWith("report"); // true

filename.startsWith("Report"); // false - case sensitive

filename.startsWith("pdf");    // false - that's at the end

let url = "https://google.com";

if (url.startsWith("https")) {

  console.log("Secure site"); // This runs
}
*2. `endsWith()`*
let filename = "photo.jpg";

filename.endsWith(".jpg");  // true

filename.endsWith(".png");  // false

filename.endsWith("jpg");   // true - the dot isn't required

let sentence = "Hello world";

sentence.endsWith("world"); // true

sentence.endsWith("World"); // false - case sensitive

*Optional start position:*

Both take a second argument for where to start/end the check.

let str = "Hello world";

// Check if "Hello" starts at index 0: default

str.startsWith("Hello"); // true

// Check if "world" ends at index 11: default is string length

str.endsWith("world"); // true

str.endsWith("world", 5); // false - only checks "Hello"

*Common uses:*
1. File type checks: `file.endsWith(".png")`

### 13. What is the difference between trim(), trimStart(), and trimEnd()?
*They all remove whitespace, but from different sides of the string.*

Whitespace = spaces, tabs `\t`, newlines `\n`. None of them change the original string.

Method | Removes from...

`trim()` | Both start + end

`trimStart()` | Start/left only

`trimEnd()` | End/right only


*Examples:*
let str = "   Hello World   ";

str.trim();      // "Hello World"

str.trimStart(); // "Hello World   "

str.trimEnd();   // "   Hello World"


*Visual breakdown:*
"   cat   "
  ↓ trim()       → "cat"

  ↓ trimStart()  → "cat   "

  ↓ trimEnd()    → "   cat"


*Other notes:*
1. *Middle spaces stay untouched*

   "  a  b  ".trim(); // "a  b"


2. *Removes tabs and newlines too*

   "\n\t  hi  \n".trim(); // "hi"


3. *Aliases*: `trimLeft()` = `trimStart()`, `trimRight()` = `trimEnd()`. Use the `Start`/`End` versions - they're the standard.

*Main use case*: Cleaning form input


let email = "   user@gmail.com  \n";
let clean = email.trim(); // "user@gmail.com"
### 14. What does repeat() do?
*`repeat()` makes copies of a string and joins them together. Returns a new string.*

*Syntax:* `string.repeat(count)`

*Basic examples:*

"ha".repeat(3);    // "hahaha"

"JS ".repeat(2);   // "JS JS "

"-".repeat(10);    // "----------"


*Key rules:*

1. *`count` must be ≥ 0*

   "hi".repeat(0);  // "" - empty string

   "hi".repeat(1);  // "hi"

   "hi".repeat(-1); // RangeError - can't be negative


2. *Non-integer gets floored*

   "a".repeat(2.7); // "aa" - becomes 2


3. *Original string unchanged*

   let word = "yo";

   let loud = word.repeat(3); // "yoyoyo"

   console.log(word); // "yo" - still the same


*Common uses:*
// Create visual separators

console.log("=".repeat(20)); // "===================="

// Padding/spacing

"Name".padEnd(10, "."); // "Name......" - uses repeat internally

// Quick test data

let row = "x ".repeat(5); // "x x x x x "


*Note*: `count` can't be `Infinity` and can't make a string longer than the JS engine allows. That throws `RangeError`.
### 15. Explain template literals with an example.
*Template literals are strings wrapped in backticks `` ` `` instead of quotes. They let you embed variables and write multi-line text without hacks.*

*3 main features:*

*1. Variable interpolation with `${}`*

No more `+` concatenation:

let name = "Alex";

let age = 25;

// Old way

"My name is " + name + " and I'm " + age;

// Template literal

`My name is ${name} and I'm ${age}`; // "My name is Alex and I'm 25"

You can put any expression inside `${}`:

let price = 20;

let tax = 0.1;

`Total: ${price + price * tax}`; // "Total: 22"

*2. Multi-line strings*

Hit enter and it keeps the line breaks:

let message = `Line 1

Line 2

Line 3`;

console.log(message);

// Line 1

// Line 2

// Line 3
With normal quotes you'd need `\n` or string concatenation.

*3. Tagged templates*

Advanced: lets a function process the template. You won't use this daily but it powers things like styled-components:
function tag(strings, value) {

  return strings[0] + value.toUpperCase();
}
let user = "sam";

tag`Hello ${user}`; // "Hello SAM"

*Quick comparison:*

let item = "coffee";

let count = 2;

// Hard to read

"Ordered " + count + " " + item + "s\nPlease wait."

// Clean

`Ordered ${count} ${item}s

Please wait.`


Template literals are standard in modern JS. Use them whenever you need variables inside strings or multiple lines.
## Part B: Output Prediction
### 1.
```
let str = "JavaScript";

console.log(str.length);
```
let str = "JavaScript";

// J a v a S c r i p t

// 1 2 3 4 5 6 7 8 9 10

console.log(str.length); // 10
### 2.
```
let str = "hello";

console.log(str.toUpperCase());
```
let str = "hello";

console.log(str.toUpperCase()); // "HELLO"

console.log(str); // "hello" - original unchanged
### 3.
```
let str = "WELCOME";

console.log(str.toLowerCase());
```
let str = "WELCOME";

console.log(str.toLowerCase()); // "welcome"

console.log(str); // "WELCOME" - original unchanged
### 4.
```
let str = "Programming";

console.log(str.slice(0, 4));
```
let str = "Programming";

// Index:  012345678910

//         P r o g r a m m i n g

console.log(str.slice(0, 4)); // "Prog"

// Gets indexes 0, 1, 2, 3 → "P", "r", "o", "g"
### 5.
```
let str = "Frontend";

console.log(str.includes("end"));
```
let str = "Frontend";

console.log(str.includes("end")); // true

// "Frontend" has "end" at indexes 5-7
### 6.
```
let str = "apple,banana,mango";

console.log(str.split(","));
```
let str = "apple,banana,mango";

console.log(str.split(",")); // ["apple", "banana", "mango"]

// Index 0: "apple"

// Index 1: "banana"

// Index 2: "mango"
### 7.
```
let str = "JavaScript";

console.log(str.charAt(2));
```
let str = "JavaScript";

// Index:  0123456789

//         J a v a S c r i p t

console.log(str.charAt(2)); // "v"

// Index 0: "J", 1: "a", 2: "v"
### 8.
```
let str = "I like cats";

console.log(str.replace("cats", "dogs"));
```
*Output: `"I like dogs"`*

`replace(searchValue, newValue)` returns a new string with the first match replaced.

let str = "I like cats";

console.log(str.replace("cats", "dogs")); // "I like dogs"

console.log(str); // "I like cats" - original unchanged

*Key points:*

1. Only replaces the _first_ occurrence: `"cats cats".replace("cats", "dogs")` → `"dogs cats"`

2. Case sensitive: `"Cats".replace("cats", "dogs")` → `"Cats"` no match

3. To replace all matches, use `replaceAll` or regex: `str.replace(/cats/g, "dogs")`

Strings are immutable, so `replace` always returns a new string instead of modifying the original.
### 9.
```
let str = "   Hello World   ";

console.log(str.trim());
```
*Output: `"Hello World"`*

`trim()` removes whitespace from both ends of a string.

let str = "   Hello World   ";

console.log(str.trim()); // "Hello World"

console.log(str); // "   Hello World   " - original unchanged

*What counts as whitespace*: spaces, tabs `\t`, and newlines `\n`.

*Related methods:*

str.trimStart()  // or trimLeft()  → "Hello World   "

str.trimEnd()    // or trimRight() → "   Hello World"

Super useful for cleaning up user input:

let userInput = "   yes   ";

if (userInput.trim() === "yes") { } // true after trim
### 10.
```
let str = "coding";

console.log(str.startsWith("co"));
```
*Output: `true`*

`startsWith(substring)` checks if a string begins with that substring. Returns a boolean.

let str = "coding";

console.log(str.startsWith("co")); // true

*Notes:*

1. Case sensitive: `"Coding".startsWith("co")` → `false`

2. Empty string always matches: `str.startsWith("")` → `true`

3. You can specify a position: `str.startsWith("di", 2)` → `true` because "coding" has "di" starting
 at index 2

*Pair it with*: `endsWith()` does the same check at the end.

"coding".endsWith("ing"); // true
## Part C: Basic Programs
### 1. Convert 'javascript' into uppercase.
Use `toUpperCase()` to convert a string to all caps.

let str = 'javascript';

console.log(str.toUpperCase()); // "JAVASCRIPT"

It returns a new string. The original `str` stays `'javascript'` because strings are immutable.
### 2. Convert 'HELLO' into lowercase.
Use `toLowerCase()` to convert a string to all lowercase.

let str = 'HELLO';

console.log(str.toLowerCase()); // "hello"

Same deal: returns a new string, doesn't change the original `str`.
### 3. Find the length of 'Frontend Development'.
Use the `.length` property to get the number of characters.

let str = 'Frontend Development';

console.log(str.length); // 22


*Note*: Spaces count as characters too. There are 8 chars in `"Frontend"`, 1 space, and 11 in 

`"Development"` → 20 + 1 + 1 = 22.

### 4. Print the first character of a string.

Two easy ways to get the first character:

*1. Using `charAt(0)`*

let str = "Frontend";

console.log(str.charAt(0)); // "F"


*2. Using bracket notation `[0]`*

let str = "Frontend";

console.log(str[0]); // "F"


Both work. Index 0 = first character. 

*Gotcha*: If the string is empty, both return `undefined` or `""` instead of erroring:

"".charAt(0) // ""

""[0] // undefined
### 5. Print the last character of a string.
Use `str.length - 1` to get the last index:

*1. Using bracket notation*

let str = "Frontend";

console.log(str[str.length - 1]); // "d"


*2. Using `charAt()`*

let str = "Frontend";

console.log(str.charAt(str.length - 1)); // "d"


*3. Modern JS: `at(-1)`*

let str = "Frontend";

console.log(str.at(-1)); // "d"


`at(-1)` is the cleanest for "last character" because negative indices count from the end.
### 6. Check whether 'Script' exists in 'JavaScript'.
Use `includes()` for a simple true/false check:

let str = 'JavaScript';

console.log(str.includes('Script')); // true


*Other options:*

1. `indexOf()` returns position or -1 if not found

str.indexOf('Script'); // 4, so it exists

str.indexOf('Python'); // -1, doesn't exist


2. `search()` with regex also works

str.search('Script'); // 4


`includes()` is the most direct. All of these are case sensitive: `'JavaScript'.includes('script')` → `false`.
### 7. Replace 'good' with 'awesome' in 'This is a good day'.
Use `replace()` to swap the first occurrence:

let str = 'This is a good day'

console.log(str.replace('good', 'awesome')); // "This is a awesome day"


*Notes:*
1. Only replaces the first match. For all matches use `replaceAll('good', 'awesome')`

2. Case sensitive: `'Good'` wouldn't match `'good'`

3. Original string unchanged - it returns a new string
### 8. Remove spaces from the beginning and end of a string.
Use `trim()` to remove whitespace from both ends:

let str = '   Hello World   ';

console.log(str.trim()); // "Hello World"


*Related methods:*
- `trimStart()` or `trimLeft()` - only leading spaces

- `trimEnd()` or `trimRight()` - only trailing spaces

'   Hello   '.trimStart(); // "Hello   "

'   Hello   '.trimEnd();   // "   Hello"


`trim()` doesn't touch spaces in the middle of the string.
### 9. Extract 'Java' from 'JavaScript'.
Use `slice()` or `substring()` with start and end indexes:

*1. `slice(start, end)`*

let str = 'JavaScript';

console.log(str.slice(0, 4)); // "Java"

End index 4 is not included, so you get indexes 0,1,2,3.

*2. `substring(start, end)`*

let str = 'JavaScript';

console.log(str.substring(0, 4)); // "Java"


*3. `substr()` - deprecated*
Avoid this one. It uses start + length instead of end index.

`slice()` is generally the go-to because it also handles negative indexes.
### 10. Convert 'HTML,CSS,JavaScript' into an array using split().
Use `split()` with `','` as the separator:

let str = 'HTML,CSS,JavaScript';

let arr = str.split(',');

console.log(arr); // ["HTML", "CSS", "JavaScript"]


`split()` breaks the string at every comma and returns an array of the pieces. 

*Note*: If there's no separator match, you get the whole string as one element: 

'HTML'.split(','); // ["HTML"]

### 11. Print 'Hi' 5 times using repeat().
Use `repeat()` with the number of times you want:

let str = 'Hi';

console.log(str.repeat(5)); // "HiHiHiHiHi"


*Note*: `repeat(0)` gives `""`, and `repeat()` with a negative number throws an error.

If you want spaces or newlines between them:

'Hi '.repeat(5); // "Hi Hi Hi Hi Hi "

'Hi\n'.repeat(5); // prints each on a new line
### 12. Check whether a string starts with 'Mr'.
Use `startsWith()` for a direct true/false check:

let str1 = 'Mr Smith';

let str2 = 'Mrs Smith';

console.log(str1.startsWith('Mr')); // true

console.log(str2.startsWith('Mr')); // true


*Note*: It's case sensitive and `'Mrs'` still starts with `'Mr'`. If you need an exact word match, combine with a space:

'Mr Smith'.startsWith('Mr '); // true

'Mrs Smith'.startsWith('Mr '); // false


Alternative: `str.indexOf('Mr') === 0` does the same thing but `startsWith()` is cleaner.
### 13. Check whether a filename ends with '.pdf'.
Use `endsWith()` for a direct true/false check:

let filename1 = 'document.pdf';

let filename2 = 'image.png';

console.log(filename1.endsWith('.pdf')); // true

console.log(filename2.endsWith('.pdf')); // false


*Notes:*
1. Case sensitive: `'DOCUMENT.PDF'.endsWith('.pdf')` is `false`. For case-insensitive check: 
`filename.toLowerCase().endsWith('.pdf')`
2. Alternative: `filename.slice(-4) === '.pdf'` works too, but `endsWith()` is clearer
### 14. Capitalize the first letter of 'hello world'.
JS doesn't have a built-in `capitalize()` method, so combine `charAt()`/`slice()` with `toUpperCase()`:

let str = 'hello world';

let capitalized = str.charAt(0).toUpperCase() + str.slice(1);

console.log(capitalized); // "Hello world"


*Breakdown:*
- `str.charAt(0)` gets `'h'`

- `toUpperCase()` makes it `'H'` 

- `str.slice(1)` gets `'ello world'`

- Combine them with `+`

*Note*: This only capitalizes the first letter of the whole string. For title case where each word 

is capitalized, you'd need to `split()`, map, and `join()`:

'hello world'.split(' ').map(w => w.charAt(0).toUpperCase() + w.slice(1)).join(' '); // "Hello World"
### 15. Find the position of 'a' in 'JavaScript'.
Use `indexOf()` to get the position of the first `'a'`:

let str = 'JavaScript';

console.log(str.indexOf('a')); // 1


*Details:*
- Indexing starts at 0, so `'J'` is 0 and `'a'` is 1

- Returns `-1` if the character isn't found

- Only gives the first match. For the last `'a'` use `lastIndexOf('a')` which returns 3

To find all positions, you'd loop with `indexOf()` or use `matchAll()`.









