https://app.codesignal.com/interview-practice/task/C8Jdyk3ybixqQdAvM/solutions

In this question, you need to implement [Array.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) by yourself.

Looping each element takes too much time.<br />
In this answer, it uses `String.split()` and this is so SMART!

```javascript
const strstr = (s, x) => {
    const devided = s.split(x);
    if (devided.length > 1) return devided[0].length;
    return -1;
}
```
