# Question
https://www.codewars.com/kata/54b42f9314d9229fd6000d9c

The goal of this exercise is to convert a string to a new string where each character in the new string is `"("` if that character appears only once in the original string, or `")"` if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.

**Examples**

```
"din"      =>  "((("
"recede"   =>  "()()()"
"Success"  =>  ")())())"
"(( @"     =>  "))((" 
```

**Notes**

Assertion messages may be unclear about what they display in some languages. If you read `"...It Should encode XXX"`, the `"XXX"` is the expected result, not the input!

# My answer

```typescript
export function duplicateEncode(word: string){
  console.log({word})
  let arr = word.split('')
  arr = arr.map(value => value.toLowerCase())
  const wordMap: { [key: string]: number} = {}
  arr.forEach((value: string) => {
    if (wordMap[value] === undefined) {
      wordMap[value] = 0
    }
    wordMap[value] += 1
  })
  
  let returnValue: string = ''
  arr.forEach((value: string) => {
    if (wordMap[value] === 1) {
      returnValue += '('
    } else {
      returnValue += ')'
    }
  })
  return returnValue
}
```