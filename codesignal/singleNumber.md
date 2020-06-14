https://app.codesignal.com/interview-practice/task/APDXraJZYfPSYqQMJ/description

`XOR` is the key.

``` javascript
function singleNumber(nums) {
  let res = 0;
  for (let num of nums) {
    res ^= num;
  }
  return res;
}
```
