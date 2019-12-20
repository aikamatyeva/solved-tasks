# solved-tasks

8 kyu Rock Paper Scissors!
https://www.codewars.com/kata/rock-paper-scissors/train/javascript
Let's play! You have to return which player won! In case of a draw return Draw!.

```javascript
const rps = (p1, p2) => {
  let map = {
    'rock': 'scissors',
    'scissors': 'paper',
    'paper': 'rock'
  };
  
  if (p1 == p2) {
    return 'Draw!';
  } else {
    return 'Player ' + (map[p1] == p2 ? 1 : 2) + ' won!';
  }
};

const rps = (p1, p2) => {
  if (p1 === p2) return 'Draw!'
  if ((p1 === 'scissors' && p2 === 'paper') || (p1 === 'rock' && p2 === 'scissors') ||(p1 === 'paper' && p2 === 'rock'))
    return 'Player 1 won!'
  if ((p2 === 'scissors' && p1 === 'paper') ||(p2 === 'rock' && p1 === 'scissors') ||(p2 === 'paper' && p1 === 'rock'))
    return 'Player 2 won!'
}
```
7 kyu Simple Fun #37: House Numbers Sum
https://www.codewars.com/kata/simple-fun-number-37-house-numbers-sum/train/javascript
At some point during the walk the boy encounters a house with number 0 written on it, which surprises him so much 
that he stops adding numbers to his total right after seeing that house.
For the given sequence of houses determine the sum that the boy will get. It is guaranteed that there will 
always be at least one 0 house on the path.
```javascript
function houseNumbersSum(n) {
  let sum = 0;
  for(let i = 0; i < n.length; i++){
    if(n[i] > 0) sum+= n[i]
    if(n[i] == 0) break;}
  return sum;
}
```

Filter out the vowels
https://www.codewars.com/kata/filter-out-the-vowels/train/javascript
```javascript
function vowelFilter (a) {
  return a.join("").replace(/[aeiou]/gi, '').split('');
};

function vowelFilter (a) {
  return a.filter(i => !"aeiou".includes(i));}
```
8 kyu Is there a vowel in there?
https://www.codewars.com/kata/is-there-a-vowel-in-there/train/javascript
Given an array of numbers, check if any of the numbers are the character codes for lower case vowels (a, e, i, o, u).
If they are, change the array value to a string of that vowel.
Return the resulting array.

```javascript
others:
a.map(x => /[aeiou]/.test(String.fromCharCode(x)) ? String.fromCharCode(x) : x);
mine:
function isVow(a){
  const a1 = ['a', 'e', 'i', 'o', 'u'];
  for(let i = 0; i < a.length; i++){
    if(a1.includes(String.fromCharCode(a[i]))){
      a[i]= String.fromCharCode(a[i]);}}
  return a;
}
```
7 kyu Sort by Last Char
https://www.codewars.com/kata/sort-by-last-char/train/javascript
Given a string of words (x), you need to return an array of the words, 
sorted alphabetically by the final character in each.
If two words have the same last letter, they returned array should show them in the order 
they appeared in the given string.
All inputs will be valid.
```javascript
function last(s){
  return s.split(' ').sort((a, b) => a.charCodeAt(a.length - 1) - b.charCodeAt(b.length - 1));
}
```

7 kyu Summing a number's digits
https://www.codewars.com/kata/summing-a-numbers-digits/train/javascript
Write a function named sumDigits which takes a number as input and returns the sum of the absolute value of each of 
the number's decimal digits. For example:
  sumDigits(10);  // Returns 1
  sumDigits(99);  // Returns 18
  sumDigits(-32); // Returns 5
```javascript
function sumDigits(n) {
  return Math.abs(n).toString().split('').map(Number).reduce((acc, curr) => acc + curr);
}

```
7 kyu Find min and max
https://www.codewars.com/kata/find-min-and-max/train/javascript
```javascript
function getMinMax(s){
  return [Math.min(...s), Math.max(...s)];
};
```
7 kyu Get initials from person name
https://www.codewars.com/kata/get-initials-from-person-name/train/javascript
Write function toInitials returns initials for a given person name. E.g: "Bill Gates" -> "B. G."
Note: initials should be separated with a space.
```javascript
function toInitials(name) {
  let s = name.split(" ").map((n) => n[0]).join(". ");
  return s+'.';
}
return s.replace(/([a-z])[a-z]+/gi, '$1.'); // others
```
8 kyu Get number from string
https://www.codewars.com/kata/get-number-from-string/train/javascript
Write a function which removes from string all non-digit characters and parse the remaining to number. E.g: "hell5o wor6ld" -> 56
```javascript
function getNumberFromString(s){
  const res = s.split('').filter((el) => Number.isInteger(+el)).join('');
  return +res.replace(/\b \b/g,'');(\b \b is to find all whitespaces)
}

function getNumberFromString(s) {
   return +s.replace(/\D/g, "");
}
```
8 kyu Regexp Basics - is it a digit?
https://www.codewars.com/kata/regexp-basics-is-it-a-digit/train/javascript
Implement String#digit? (in Java StringUtils.isDigit(String)), 
which should return true if given object is a digit (0-9), false otherwise.
```javascript
 String.prototype.digit = function() {
    return /^[0-9]$/.test(this);
 };

mine 
String.prototype.digit = function() {
       let a = this.replace(/\s/g)
       return /\b\d\b/g.test(a) ? true : false;
     };
```
7 kyu Check three and two
https://www.codewars.com/kata/check-three-and-two/train/javascript
Given an array with exactly 5 strings "a", "b" or "c" (chars in Java, characters in Fortran), 
check if the array contains three and two of the same values.

Examples
["a", "a", "a", "b", "b"] ==> true  // 3x "a" and 2x "b"
["a", "b", "c", "b", "c"] ==> false // 1x "a", 2x "b" and 2x "c"
["a", "a", "a", "a", "a"] ==> false // 5x "a"
```javascript
my version 
function checkThreeAndTwo(arr) {
  console.log(arr)
  let a = 0;
  let b = 0;
  let c = 0;

  for(let i = 0; i < arr.length; i++){
    if(arr[i] == 'a'){
      a++;
    }
    if(arr[i] == 'b'){
      b++;
    }
    if(arr[i] == 'c'){
      c++;
    }
  }

  if ((a > 2 && b > 1) || (a > 1 && b > 2)){
    return true;
  } else if ((a > 1 && c > 2) || (a > 2 && c > 1)){
    return true;
  } else if ((b > 1 && c > 2) || (b > 2 && c > 1)){
    return true;
  }else {
    return false;
  }
}

LarOvch
function checkThreeAndTwo(arr) {
  let obj ={};
  for (let i = 0; i < arr.length; i++){
    if (obj[arr[i]]) obj[arr[i]] ++;
    else obj[arr[i]] = 1;
  }
  for (let i in obj) {
    if (obj[i] < 2 || obj[i] > 3) return false;
  }
  return true;
}

another way 
function checkThreeAndTwo(arr) {
  let a = 0;
  let b = 0;
  let c = 0;
  for(let i = 0; i < arr.length; i++){
    if(arr[i] == 'a') a++;
    if(arr[i] == 'b') b++;
    if(arr[i] == 'c') c++;
  }
  return [a,b,c].includes(3) && [a,b,c].includes(2) ? true : false;
}
```
7 kyu Make a function that does arithmetic!
https://www.codewars.com/kata/make-a-function-that-does-arithmetic/train/javascript
Given two numbers and an arithmetic operator (the name of it, as a string), 
return the result of the two numbers having that operator used on them.
a and b will both be positive integers, and a will always be the first number in the operation, 
and b always the second.

The four operators are "add", "subtract", "divide", "multiply".

A few examples:

arithmetic(5, 2, "add")      => returns 7
arithmetic(5, 2, "subtract") => returns 3
arithmetic(5, 2, "multiply") => returns 10
arithmetic(5, 2, "divide")   => returns 2.5
```javascript
const arithmetic = (a, b, operator) => ({
  'add'     : a + b,
  'subtract': a - b,
  'multiply': a * b,
  'divide'  : a / b
}[operator]);
```
```javascript
function arithmetic(a, b, operator){
  switch (operator) {
  case 'add':
    return (a + b);
    break;
  case 'subtract':
    return (a - b);
    break;
  case 'multiply':
    return (a * b);
    break;
  case 'divide':
    return (a / b);
    break;
}
}
```

7 kyu makeBackronym
https://www.codewars.com/kata/makebackronym/train/javascript 
back·ro·nym
An acronym deliberately formed from a phrase whose initial letters spell out a particular word or words, 
either to create a memorable name or as a fanciful explanation of a word's origin.
"Biodiversity Serving Our Nation", or BISON
(from https://en.oxforddictionaries.com/definition/backronym)
Complete the function to create backronyms. Transform the given string (without spaces) to a backronym, using the preloaded dictionary and return a string of words, 
separated with a single space (but no trailing spaces).
The keys of the preloaded dictionary are uppercase letters A-Z and the values are predetermined words, for example:
dict["P"] == "perfect"
```javascript
function makeBackronym (str){
  return str.toUpperCase().split('').map(word => dict[word]).join(' ');
};

var dict = {
  A: 'awesome',
  B: 'beautiful',
  C: 'confident',
  D: 'disturbing',
  E: 'eager',
  F: 'fantastic',
  G: 'gregarious',
  H: 'hippy',
  I: 'ingestable',
  J: 'joke',
  K: 'klingon',
  L: 'literal',
  M: 'mustache',
  N: 'newtonian',
  O: 'oscillating',
  P: 'perfect',
  Q: 'queen',
  R: 'rant',
  S: 'stylish',
  T: 'turn',
  U: 'underlying',
  V: 'volcano',
  W: 'weird',
  X: 'xylophone',
  Y: 'yogic',
  Z: 'zero',
};

function makeBackronym (str){
  return str.toUpperCase().split('').map(word => dict[word]).join(' ')
};
```
8 kyu Duck Duck Goose
https://www.codewars.com/kata/duck-duck-goose/train/javascript
Task: Given an array of Player objects (an array of associative arrays in PHP) and an index (1-based), 
return the name of the chosen Player(name is a property of Player objects, e.g Player.name)
Example:
duck_duck_goose([a, b, c, d], 1) should return a.name
duck_duck_goose([a, b, c, d], 5) should return a.name
duck_duck_goose([a, b, c, d], 4) should return d.name
```javascript
function duckDuckGoose(players, goose) {
  return players[(goose - 1) % players.length].name;
}
```
8 kyu Squash the bugs
https://www.codewars.com/kata/squash-the-bugs/train/javascript
Simple challenge - eliminate all bugs from the supplied code so that the code runs and outputs the 
expected value. Output should be the length of the longest word, as a number.

There will only be one 'longest' word.
```javascript
function findLongest(str) {
  let spl = str.split(" ");
  let longest = 0
  for (let i = 0; i < spl.length; i++) {
    if (spl[i].length > longest) {
        longest = spl[i].length
    }
}  return longest;
}
```
8 kyu Name Shuffler
https://www.codewars.com/kata/name-shuffler/train/javascript
```javascript
function nameShuffler(str){
  return str.split(' ').reverse().join(' ');
}

const arr = str.split(' ');
return [arr[0], arr[1]] = [arr[1], arr[0]].join(' ');
```
7 kyu Highest and Lowest
https://www.codewars.com/kata/highest-and-lowest/train/javascript
```javascript
function highAndLow(str){
  const arr = str.split(' ').sort((a, b) => b - a);
  return [arr[0], arr[arr.length - 1]].join(' ');
}
```
8 kyu Exclamation marks series #2: Remove all exclamation marks from the end of sentence
https://www.codewars.com/kata/exclamation-marks-series-number-2-remove-all-exclamation-marks-from-the-end-of-sentence/train/javascript
Remove all exclamation marks from the end of sentence.
```javascript
function remove(s){
  return s.replace(/!+$/g,"");
}
```
Replace dot
```javascript
s.replace(/\./g,"-")
```
8 kyu Fake Binary
https://www.codewars.com/kata/fake-binary/train/javascript
Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. 
Return the resulting string.
```javascript
function fakeBin(s){
  return s.replace(/[1-4]/g, 0).replace(/[5-9]/g, 1);
}
```
8 kyu Correct the mistakes of the character recognition software
https://www.codewars.com/kata/correct-the-mistakes-of-the-character-recognition-software/train/javascript
Character recognition software is widely used to digitise printed texts. Thus the texts can be edited, searched and stored on a computer.
When documents (especially pretty old ones written with a typewriter), are digitised character recognition softwares often make mistakes.
Your task is correct the errors in the digitised text. You only have to handle the following mistakes:
S is misinterpreted as 5
O is misinterpreted as 0
I is misinterpreted as 1
```javascript
function correct(str){
	return str.replace(/[5]/g, 'S').replace(/[0]/g, 'O').replace(/[1]/g, 'I');
}
```
7 kyuComplementary DNA
https://www.codewars.com/kata/complementary-dna/train/javascript
```javascript
function DNAStrand(dna){
  return dna.replace(/A/g, 't').replace(/T/g, 'a').replace(/C/g, 'g').replace(/G/g, 'c').toUpperCase();
}
function DNAStrand(str) {
    let res = '';
    for (let i = 0; i < str.length; i++) {
        if (str[i] == 'A') {
            res += 'T';
        } else if (str[i] == 'T') {
            res += 'A';
        } else if (str[i] == 'G') {
            res += 'C';
        } else if (str[i] == 'C') {
            res += 'G';
        } else {
            res += str[i];
        }
    }
    return res;
}
```
7 kyu Credit Card Mask
https://www.codewars.com/kata/credit-card-mask/train/javascript
Usually when you buy something, you're asked whether your credit card number, phone number or answer to your most secret question is still correct. 
However, since someone could look over your shoulder, 
you don't want that shown on your screen. Instead, we mask it.
Your task is to write a function maskify, which changes all but the last four characters into '#'.
```javascript
function maskify(s) {
  if(s.length <= 3) return s;
  const sl = (s.slice(0, s.length - 4)).length;
  let res = '';
  for(let i = 0; i < sl; i++){
    res+= s[i].replace(s[i], '#');
  }
  return res + s.slice(s.length -4);
}

```
7 kyu Don't give me five!
https://www.codewars.com/kata/dont-give-me-five/train/javascript
In this kata you get the start number and the end number of a region and should return the count of all numbers except numbers with a 5 in it. 
The start and the end number are both inclusive!
Examples:
1,9 -> 1,2,3,4,6,7,8,9 -> Result 8
4,17 -> 4,6,7,8,9,10,11,12,13,14,16,17 -> Result 12
The result may contain fives. ;-)
The start number will always be smaller than the end number. Both numbers can be also negative!

I'm very curious for your solutions and the way you solve it. Maybe someone of you will find an easy pure mathematics solution.

Have fun coding it and please don't forget to vote and rank this kata! :-)

I have also created other katas. Take a look if you enjoyed this kata!
```javascript
function dontGiveMeFive(start, end){
  let count = 0;
  for(let i = start; i <= end; i++){
    if(!i.toString().includes(5)){
      count++;}
  }
  return count;
}
```

7 kyu Thinking & Testing : Something capitalized
https://www.codewars.com/kata/thinking-and-testing-something-capitalized/train/javascript
```javascript
function testit(s){
  if (s.length === 0) return s;
  let arr = s.split(' ');
  for (let i = 0; i < arr.length; i++) {
    let str = arr[i];
    if (str.length > 1) {
        arr[i] = str.substring(0, str.length - 1) + str.substring(str.length - 1).toUpperCase();
    } else {
        arr[i] = str.toUpperCase();
    }
}  return arr.join(' ');
}
```

7 kyu Mumbling
https://www.codewars.com/kata/mumbling/train/javascript
This time no story, no theory. The examples below show you how to write function accum
```javascript
function accum(s) {
	return s.split('').map((char, index) => {
      let repeat = char.repeat(index + 1);
      return (repeat.charAt(0).toUpperCase() +repeat.slice(1).toLowerCase())
    }).join('-');
}

another one:
function accum(s) {
  let array = [];
  for (i = 0; i < (s.length); i++) {
    array.push(s.charAt(i).toUpperCase() + s.charAt(i).toLowerCase().repeat(i));
  };
  return array.join("-");
}

```

8 kyu Regex count lowercase letters
https://www.codewars.com/kata/regex-count-lowercase-letters/train/javascript
Your task is simply to count the total number of lowercase letters in a string.
```javascript
function lowercaseCount(str){
  let count = 0;
  for (let i = 0; i < str.length; i++) {
     if (/[a-z]+/.test(str[i])){
     count++;}
  }  
  return count;
}
```

7 kyu Numbers to Letters
https://www.codewars.com/kata/numbers-to-letters/train/javascript
Given an array of numbers, you must return a string. The numbers correspond to the letters of the 
alphabet in reverse order: a=26, z=1 etc. You should also account for '!', '?' and ' ' that are 
represented by '27', '28' and '29' respectively.
All inputs will be valid.
```javascript
function switcher(x){
  return x.reduce((word, number) => `${word}${' ?!abcdefghijklmnopqrstuvwxyz'[29 - number]}`, '');
}
```

8 kyu SpeedCode #2 - Array Madness
https://www.codewars.com/kata/speedcode-number-2-array-madness/train/javascript
Given two integer arrays a, b, both of length >= 1, create a program that returns true if the sum of the squares of each element 
in a is strictly greater than the sum of the cubes of each element in b.
```javascript
function arrayMadness(a, b) {
  return a.reduce((total, num) => total + num ** 2, 0) > b.reduce((total, num) => total + num ** 3, 0);
}
```
8 kyu Convert number to reversed array of digits
https://www.codewars.com/kata/convert-number-to-reversed-array-of-digits/train/javascript
```javascript
function digitize(n) {
  return Array.from(String(n), Number).reverse();
}
```

7 kyu Train to remove duplicates from an array with filter()
https://www.codewars.com/kata/train-to-remove-duplicates-from-an-array-with-filter/train/javascript
In this kata your task is to remove all the duplicates from the array using a standart build-in method - Array.prototype.filter(); 
return the array containing unique values only.
```javascript
function unique(arr) {
  const nonDuplicates = arr.filter((el, i) => i === arr.indexOf(el));
  return nonDuplicates;
}
```

7 kyu Find Duplicates
https://www.codewars.com/kata/find-duplicates/train/javascript
451088% of 194897 of 1,589loickreitmann2 Issues Reported
JavaScript
Node v8.1.3
VIM
EMACS
Instructions
Output
Past Solutions
Given an array, find the duplicates in that array, and return a new array of those duplicates. T
he elements of the returned array should appear in the order when they first appeared as duplicates.
Note: numbers and their corresponding string representations should not be treated as duplicates (i.e., '1' !== 1).
```javascript
function duplicates(arr) {
  const duplicates = arr.filter((el, i) => i !== arr.indexOf(el) && i === arr.lastIndexOf(el));
  return duplicates;
}
```
7 kyu Find how many times did a team from a given country win the Champions League?
https://www.codewars.com/kata/find-how-many-times-did-a-team-from-a-given-country-win-the-champions-league/train/javascript
Create a function that takes two arguments:
1) An array of objects which feature the season, the team and the country of the Champions League winner.
2) Country (as a string, for example, 'Portugal')
You function should then return the number which represents the number of times a team from a given country has won. 
Return 0 if there have been no wins.
```javascript
function countWins(winnerList, country) {
  return  winnerList.filter(el => el.country == country).length;
}
example:
const arr = [
  { season: '1996–97', team: 'Borussia Dortmund', country: 'Germany' },
  { season: '1997–98', team: 'Real Madrid', country: 'Spain' },
  { season: '1998–99', team: 'Manchester United', country: 'England' },
  { season: '1999–00', team: 'Real Madrid', country: 'Spain' },
  { season: '2000–01', team: 'Bayern Munich', country: 'Germany' },
  { season: '2001–02', team: 'Real Madrid', country: 'Spain' },
  { season: '2002–03', team: 'Milan', country: 'Italy' },
  { season: '2003–04', team: 'Porto', country: 'Portugal' },
  { season: '2004–05', team: 'Liverpool', country: 'England' },
  { season: '2005–06', team: 'Barcelona', country: 'Spain' },
  { season: '2006–07', team: 'Milan', country: 'Italy' },
  { season: '2007–08', team: 'Manchester United', country: 'England' },
  { season: '2008–09', team: 'Barcelona', country: 'Spain' },
  { season: '2009–10', team: 'Internazionale', country: 'Italy' },
  { season: '2010–11', team: 'Barcelona', country: 'Spain' },
  { season: '2011–12', team: 'Chelsea', country: 'England' },
  { season: '2012–13', team: 'Bayern', country: 'Germany' },
  { season: '2013–14', team: 'Real Madrid', country: 'Spain' },
  { season: '2014–15', team: 'Barcelona', country: 'Spain' },
  { season: '2015–16', team: 'Real Madrid', country: 'Spain' }
];

function countWins(winnerList, country) {
  return  winnerList.filter(el => el.country == country).length
}

console.log(countWins(arr, 'Spain'));


```
6 kyu Array.diff
https://www.codewars.com/kata/array-dot-diff/train/javascript
Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.
It should remove all values from list a, which are present in list b.

array_diff([1,2],[1]) == [2]
If a value is present in b, all of its occurrences must be removed from the other:

array_diff([1,2,2,2,3],[2]) == [1,3]
```javascript
function array_diff(a, b) {
  const arr = a.filter((el) => !b.includes(el));
  return arr;
}
```
7 kyu JavaScript Array Filter
https://www.codewars.com/kata/javascript-array-filter/train/javascript
JavaScript Arrays support a filter function (starting in JavaScript 1.6). 
Use the filter functionality to complete the function given.

The solution would work like the following:
```javascript
function getEvenNumbers(arr){
  const arr2 = arr.filter((el, i) => el % 2 == 0);
  return arr2;
}
```

7 kyu filterEvenLengthWords
https://www.codewars.com/kata/filterevenlengthwords
Given an array of strings, "filterEvenLengthWords" returns an array containing only the elements of 
the given array whose length is an even number.
var output = filterEvenLengthWords(['word', 'words', 'word', 'words']);

console.log(output); // --> ['word', 'word']
```javascript
function filterEvenLengthWords(arr) {
  const arr2 = arr.filter((el, i) => el.length % 2 == 0);
  return arr2;
}
```
8 kyu Removing Elements
https://www.codewars.com/kata/removing-elements
Take an array and remove every second element out of that array. 
Always keep the first element and start removing with the next element.
```javascript
function removeEveryOther(arr){
 const arr2 = arr.filter((el, i) => i % 2 == 0);
  return arr2;
}
```
8 kyu Find numbers which are divisible by given number
Complete the function which takes two arguments and returns all numbers which are divisible by the given divisor. 
First argument is an array of numbers and the second is the divisor.
   ```javascript
function divisibleBy(arr, divisor){
  const arr2 = arr.filter((el) => el % divisor === 0);
  return arr2;
}
```
8 kyu Find Maximum and Minimum Values of a List
https://www.codewars.com/kata/find-maximum-and-minimum-values-of-a-list/train/javascript
Your task is to make two functions, max and min (maximum and minimum in PHP and Python) that take a(n) array/vector of integers list as input and outputs, 
respectively, the largest and lowest number in that array/vector.
```javascript
let min = function(list){
    return Math.min(...list);
};
let max = function(list){
    return Math.max(...list);
};
```

7 kyu Find the divisors!
https://www.codewars.com/kata/find-the-divisors/train/javascript
Create a function named divisors/Divisors that takes an integer n > 1 and 
returns an array with all of the integer's divisors(except for 1 and the number itself), from smallest to largest. 
If the number is prime return the string '(integer) is prime' (null in C#) (use Either String a in Haskell and Result<Vec<u32>, String> in Rust).

```javascript
function divisors(n) {
  let arr = []
  for (let i = 2; i <= Math.floor(n / 2); ++i) if (n % i == 0) arr.push(i);
  return arr.length ? arr : n + ' is prime'
}
```
8 kyu Total amount of points
https://www.codewars.com/kata/total-amount-of-points/train/javascript
Our football team finished the championship. 
The result of each match look like "x:y". Results of all matches are recorded in the collection.

For example: ["3:1", "2:2", "0:1", ...]

Write a function that takes such collection and counts the points of 
our team in the championship. Rules for counting points for each match:

if x>y - 3 points
if x<y - 0 point
if x=y - 1 point
Notes:

there are 10 matches in the championship
0 <= x <= 4
0 <= y <= 4
```javascript
function points(games) {
 let sum = 0;
 for(let i = 0; i < games.length; i++) {
   let a = games[i].split(':');
   if(a[0] > a[1]) {
     sum += 3;
   } else if(a[0] == a[1]) {
     sum += 1;
   } else { sum = sum } 
  
 }
 return sum;
}

```

7 kyu Is every value in the array an array?
https://www.codewars.com/kata/difference-of-volumes-of-cuboids/train/javascript
This should only test the second array dimension of the array. 
The values of the nested arrays don't have to be arrays.

```javascript
const arrCheck = a => a.every(Array.isArray);
```

7 kyu Squares sequence
https://www.codewars.com/kata/57e92e91b63b6cbac20001e5/solutions/javascript
Complete the function that returns an array of length n, 
starting with the given number x and the squares of the previous number. 
If n is negative or zero, return an empty array/list.

```javascript
function squares(x, n) {
  let res = [];
  for(let i=0; i<n; i++){
    res.push(x);
    x*= x;
  }
  return res;
}
```



