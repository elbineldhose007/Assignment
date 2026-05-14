# __📁05.JAVASCRIPT Assignment-Condition💻__

### __1. Check if a number is positive or negative__
### Concept: if
### Problem:
### Write a program to check if a number is positive.
### Example:
### Input: 5 → Output: "Positive"

__Answer;__

*Concept*: `if` statements let you run code only when a condition is true.

### Check positive or negative

*JavaScript:*
let num = 5;

if (num > 0) {

  console.log("Positive");

} else if (num < 0) {

  console.log("Negative");

} else {

  console.log("Zero");
}

// Output: Positive
### __2. Check if a number is even or odd__
### Concept: if-else

__Answer;__

let num = 7;

if (num % 2 === 0) {
  console.log("Even");
} else {
  console.log("Odd");
}

// Output: Odd
### _3. Check if a person is eligible to vote
### Concept: if-else
### Age ≥ 18 → “Eligible” otherwise “Not eligible”.

|__Answer;__

*Concept*: `if-else` with a comparison operator `>=`

### Vote eligibility check

*JavaScript:

let age = 20;

if (age >= 18) {

  console.log("Eligible");

} else {

  console.log("Not eligible");
}

// Output: Eligible

### __4. Find the largest of two numbers__
### Concept: if-else

__Answer;__

let a = 12;

let b = 9;

if (a > b) {

  console.log(a + " is larger");

} else if (b > a) {

  console.log(b + " is larger");

} else {

  console.log("Both are equal");
}

// Output: 12 is larger
### __5. Find the largest of three numbers__
### Concept: if-else if-else

__Answer;__

*Concept*: `if-else if-else` chains let you test multiple conditions in order.

### Find largest of three numbers

JavaScript:
let a = 12;

let b = 25;

let c = 18;

if (a >= b && a >= c) {

  console.log(a + " is largest");

} else if (b >= a && b >= c) {

  console.log(b + " is largest");

} else {

  console.log(c + " is largest");
}

// Output: 25 is largest
### __6. Check if a character is a vowel or consonant__
### Concept: if-else if-else

__Answer;__

*Concept*: `if-else if-else` to test multiple character conditions

### Check vowel or consonant

*JavaScript:*

let char = 'e';

char = char.toLowerCase(); // handle uppercase too

if (char === 'a' || char === 'e' || char === 'i' || char === 'o' || char === 'u') {

  console.log("Vowel");

} else if (char >= 'a' && char <= 'z') {

  console.log("Consonant");

} else {

  console.log("Not a letter");
}

// Output: Vowel
1. Convert to lowercase first so `A` and `a` both work

2. Second check makes sure it's actually a letter - prevents `1` or `@` from being called "Consonant"

3. Vowels: `a, e, i, o, u`. Everything else a-z is consonant
### __7. Grade the student based on marks__
### Concept: if-else if-else
### Example:
### 90–100 → A
### 80–89 → B
### 70–79 → C
### else → Fail

__Answer;__

let marks = 85;

if (marks >= 90 && marks <= 100) {

  console.log("Grade A");

} else if (marks >= 80 && marks <= 89) {

  console.log("Grade B");

} else if (marks >= 70 && marks <= 79) {

  console.log("Grade C");

} else if (marks >= 0 && marks < 70) {

  console.log("Fail");

} else {

  console.log("Invalid marks");
}

// Output: Grade B
### __8. Check if a number is divisible by both 3 and 5__
### Concept: logical AND (&&)

__Answer;__

let num = 15;

if (num % 3 === 0 && num % 5 === 0) {

  console.log("Divisible by both 3 and 5");

} else {

  console.log("Not divisible by both");

}

// Output: Divisible by both 3 and 5

### __9. Check if a number is in a range (10 to 50)__
### Concept: logical AND (&&)

__Answer;__

*Concept*: Logical AND `&&` to check if a number meets both lower and upper bounds

### Check if number is in range 10 to 50

*JavaScript:*

let num = 25;

if (num >= 10 && num <= 50) {

  console.log("In range");

} else {

  console.log("Out of range");
}

// Output: In range
*Python:*

### Python bonus: you can also write it as
### if 10 <= num <= 50:
*How it works*: Both conditions must be true.  
- `25 >= 10` → true  
- `25 <= 50` → true  
- `true && true` → "In range"

*Test it:*
- `num = 10` → "In range" - boundaries included
- `num = 50` → "In range" 
- `num = 9` → "Out of range"
- `num = 51` → "Out of range"

### __10. Check if a year is a leap year__
### Concept: combined conditions (&&, ||)

__Answer;__

*Concept*: Combined conditions with `&&` and `||` - leap years have specific rules

### Check if a year is a leap year

*Leap year rules:*
1. Divisible by 400 → leap year
2. Divisible by 4 but NOT by 100 → leap year
3. Everything else → not leap

*JavaScript:*

let year = 2024;

if (year % 400 === 0 || (year % 4 === 0 && year % 100 !== 0))
 {

  console.log(year + " is a leap year");

} else {

  console.log(year + " is not a leap year");
}

// Output: 2024 is a leap year

*Test cases:*
- `2000` → leap - divisible by 400
- `1900` → not leap - divisible by 100 but not 400  
- `2024` → leap - divisible by 4, not by 100
- `2023` → not leap

*Why the parentheses*: `&&` runs before `||`, so we group `year % 4 == 0 && year % 100 != 0` to check that combo first.







