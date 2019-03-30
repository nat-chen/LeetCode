# Two Sum

## Question Description
* Given an array of integers, return indices of the two numbers such that they add up to a specific target.
* You may assume that each input would have exactly one solution, and you may not use the same element twice.
```js
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1]
```

## Solution
  
### 方法1：暴力破解

#### 思路
* 两个 for 循环遍历，暴力破解

```js
const twoSum = function(nums, target) {
  let length = nums.length;
  let balance = current = 0;
  for (var i = 0; i < length; i++) {
    balance = target - nums[i];
    for (var j = i + 1; j < length; j++) {
      current = nums[j];
      if (current === balance) {
        return [i, j];
      }
    }
  }
};
```

### 方法2：哈希，一次性遍历
* 利用哈希表对已遍历的项记录，遍历后续的每个值时，先去查找哈希表是否出现；若找到则返回给定格式的值，否则遍历下一个数组项。

```js
const twoSum = function(nums, target) {
  let hashTable = {};
  let balance = current = 0;
  for (var i = 0; i < length; i++) {
    current = nums[i];
    balance = target - current;
    if (current in hashTable) {
      return [nums[hashTable[current]], i];
    }
    hashTable[current] = i;
  }
};
<<<<<<< HEAD
```
=======
>>>>>>> cbd83183ec225ebc8f37f23bc271148f46fd6db9
