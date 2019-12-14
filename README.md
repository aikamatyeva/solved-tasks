# solved-tasks

7 kyu Squares sequence

Complete the function that returns an array of length n, 
starting with the given number x and the squares of the previous number. 
If n is negative or zero, return an empty array/list.

Solution :
function squares(x, n) {
  let res = [];
  for(let i=0; i<n; i++){
    res.push(x);
    x*= x;
  }
  return res;
}

