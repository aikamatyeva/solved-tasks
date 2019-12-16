# solved-tasks

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



