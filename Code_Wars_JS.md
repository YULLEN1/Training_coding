# 8kyu/ Count by X

Create a function with two arguments that will return an array of the first n multiples of x.

Assume both the given number and the number of times to count will be positive numbers greater than 0.

Return the results as an array or list ( depending on language ).

Examples
countBy(1,10) === [1,2,3,4,5,6,7,8,9,10]

countBy(2,5) === [2,4,6,8,10]

## Решение
 ```
 function countBy(x, n) { 
 	var z = [];
 	for (var i = 1; i <= n; i++) {
 		z.push(x * i);
 	} 
 	return z; 
 }
```

 

 # 8kyu/ Find the smallest integer in the array
 Given an array of integers your solution should find the smallest integer.

 For example:

 Given [34, 15, 88, 2] your solution will return 2
 
 Given [34, -345, -1, 100] your solution will return -345
 You can assume, for the purpose of this kata, that the supplied array will not be empty.

## Решение № 1
```
 function findSmallestInt(arr) {
 	let min = arr[0];
 	for (let i = 0; i < arr.length; i++) {
 		if (arr[i] < min) {
 			min = arr[i];
 		}
 	}
 	return min;
 }
```
## Решение № 2
```
function findSmallestInt(arr) {
  	return Math.min(...arr);
  }
```

