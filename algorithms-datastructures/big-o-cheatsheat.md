---
title: big-o-cheatsheat
date: 11/02/2025
tags:
  - big-o
---
# big-o-cheatsheat

## O(1)

```
function add(a, b) {
	return a + b;
}
```

No matter how big the inputs are it is just one operation


## O(log n)

```
function binarySearch(arr, x) {
	let start = 0;
	let end = arr.length - 1;
	
	while(start <= end) {
		let mid = Math.floor(start+end/2);
		
		if(arr[mid] === x) return true;
		
		if(arr[mid] < x) {
			start = mid + 1;
		} else {
			end = mid - 1;
		}
	}
	
	return false;
}

```

Every Iteration it cuts the result in half


## O(n) 

```
function printArr(arr) {
	arr.forEach((i) => {
		console.log(i);
	})
}

```

Iterates through each item of the array

```
function printArrTwice(arr) {
	arr.forEach((i) => {
		console.log(i);
	})
	
	arr.forEach((i) => {
		console.log(i*2);
	})
}

```

Iterates through array twice.  Technically is O(2n), but constant is dropped so we just say O(n)

## O(a+b)

```
function printDiffArr(arr1, arr2) {
	arr1.forEach((i) => {
		console.log(i);
	})
	
	arr2.forEach((i) => {
		console.log(i*2);
	})
}

```

Two different arrays so size of the arrays can be different O(a+b)


## O(n log n)


Merge sort - one operation that loops through the array and another is dividing the array in half.


## O(n^2)

```
function numDups(arr) {
	let dups = 0;
	for(let i = 0; i<arr.length; i++) {
		for(let j = 0; j<arr.length; j++) {
			console.log(arr[i] * arr[j]);
		}
	}
}

```

Nested loops with the same array will be O(n^2).  If arrays are different than it will be O(ab), since each array can be of different length.

## O(2^n)


```
function fibonacci(n){
	 if(n <= 1) {
	 	return n 
	 }

	 
	 return fibonacci(n - 1) + fibonacci(n - 2)
}

```

On each pass it makes 2 more calls.  First time there is 2, then at next pass there will be 4, then 8, and so on until we reach the base case.

202511022112
