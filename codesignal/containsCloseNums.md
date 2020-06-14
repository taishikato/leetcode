https://app.codesignal.com/interview-practice/task/njfXsvjRthFKmMwLC/description

```javascript
function containsCloseNums(nums, k) {
    const map = {};
    
    for (let i = 0; i < nums.length; i++) {
        if (map[nums[i]] === undefined) {
            map[nums[i]] = i;
            continue;
        }
        if (Math.abs(map[nums[i]] - i) <= k) {
            return true;
        } else {
            map[nums[i]] = i;
        }
    }
    return false;
}
```
