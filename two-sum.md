## Two Sum [link](https://leetcode.com/problems/two-sum/)

 > Given an array of integers, find two numbers such that they add up to a specific target number.

 > The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2. Please note that your returned answers (both index1 and index2) are not zero-based.

 > You may assume that each input would have exactly one solution.

 > Input: numbers={2, 7, 11, 15}, target=9
 > Output: index1=1, index2=2


O(n)
```javascript 
var twoSum = function(nums, target) {
	var myMap = new Map();
	
    for(var i=0; i<nums.length; i++){
        myMap.set(nums[i], i+1);
    }
	for(var j=0; j<nums.length; j++) {
	    //console.log(myMap.get(target-nums[j]));

		if(myMap.get(target-nums[j]) !== undefined && myMap.get(target-nums[j])> j+1 ) {
			return [j+1, myMap.get(target-nums[j])];
		}
	}
};

```

O(n^2)
```javascript 
var twoSum = function(nums, target) {
	for(var i=0; i<nums.length; i++) {
		for(var j=i+1; j<nums.length; j++) {
			if(nums[i]+nums[j] == target) {
				return [i+1, j+1];
			} 
			
		}
	}
};

```
