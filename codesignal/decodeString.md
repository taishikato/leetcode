https://app.codesignal.com/interview-practice/task/dYCH8sdnxGf5aGkez/description

```javascript
function decodeString(s) {
    const numStack = [];
    const wordStack = [''];
    let num = 0;

    for(const char of s) {
        if(/\d/.test(char)) {
             // 10 * num is for multiple digits
            num = 10 * num + parseInt(char);
        } else {
            if(char === '[') {
                numStack.push(num);
                wordStack.push('');
                num = 0;
            } else if(char === ']') {
                const repeater = numStack.pop();
                const word = wordStack.pop();
                wordStack[wordStack.length - 1] += word.repeat(repeater);
            } else {
                wordStack[wordStack.length - 1] += char;
            }
        }
    }

    return wordStack.pop();
}
```
