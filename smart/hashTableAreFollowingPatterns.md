https://app.codesignal.com/interview-practice/topics/hash-tables

mmm This is so SMART.

```javascript
function areFollowingPatterns(strings, patterns) {
    for (var i = 0; i < strings.length; i++) {
        if(patterns.indexOf(patterns[i]) !== strings.indexOf(strings[i])) return false;
    }
    return true;
}
```
