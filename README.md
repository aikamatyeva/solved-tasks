# solved-tasks

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



