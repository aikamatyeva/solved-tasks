# solved-tasks
8 kyu Total amount of points
https://www.codewars.com/kata/total-amount-of-points/train/javascript
Our football team finished the championship. 
The result of each match look like "x:y". Results of all matches are r
ecorded in the collection.

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



