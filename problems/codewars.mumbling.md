# Question
https://www.codewars.com/kata/5667e8f4e3f572a8f2000039

This time no story, no theory. The examples below show you how to write function `accum`:

**Examples:**

```
accum("abcd") -> "A-Bb-Ccc-Dddd"
accum("RqaEzty") -> "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt") -> "C-Ww-Aaa-Tttt"
```

The parameter of accum is a string which includes only letters from `a..z` and `A..Z`.

# My answer

```javascript
function accum(s) {
	const arr = s.split('')
  const mappedArr = arr.map((str, index) => {
    lowerCases = ''
    for (let i = 0; i < index; i++) {
      lowerCases += str.toLowerCase()
    }
    return `${str.toUpperCase()}${lowerCases}`
  })
  return mappedArr.join('-')
}
```