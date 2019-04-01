# Reverse Integer

## Question Description
* Given a 32-bit signed integer, reverse digits of an integer.
* Note: Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−2^31,  2^31 − 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.
```js
Input: 123
Output: 321

Input: 120
Output: 21

Input: -123
Output: -321
```

## Solution
  
### 方法1

#### 思路
* 迭代每一位数，分别求商 (/) 和求余 (%)

```js
const reverse = function(number) {
  let reversedNumber = 0;
  let maxNumber = Math.pow(2, 31) - 1;
  let minNumber = Math.pow(-2, 31);
  while (number !== 0) {
    reversedNumber = reversedNumber * 10 + number % 10; //保存最后一位
    number = parseInt(x / 10); //过滤最后一位
  }
  if (reversedNumber > maxNumber || reversedNumber < minNumber) {
    return 0;
  }
  return reversedNumber;
}
```
