# Question
## Decipher this!
https://www.codewars.com/kata/581e014b55f2c52bb00000f8

You are given a secret message you need to decipher. Here are the things you need to know to decipher it:

For each word:

* the second and the last letter is switched (e.g. `Hello` becomes `Holle`)
* the first letter is replaced by its character code (e.g. `H` becomes `72`)

Note: there are no special characters used, only letters and spaces

Examples
```javascript
decipherThis('72olle 103doo 100ya'); // 'Hello good day'
decipherThis('82yade 115te 103o'); // 'Ready set go'
```

# My answer
```typescript
export function decipherThis(str: string): string {
  const arr = str.split(' ')
  return arr.map(str => {
    const strArr = str.split('')
    const numberArr = strArr.filter(val => !isNaN(val as any))
    const firstLetter = String.fromCharCode(Number(numberArr.join('')))
    strArr.splice(0, numberArr.length)
    const secondVal = strArr[0]
    strArr[0] = strArr[strArr.length - 1]
    strArr[strArr.length - 1] = secondVal
    return `${firstLetter}${strArr.join('')}`
  }).join(' ')
}
```