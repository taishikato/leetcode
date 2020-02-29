# Question

## Srot the inner ctonnet in dsnnieedcg oredr
https://www.codewars.com/kata/5898b4b71d298e51b600014b

#Srot the inner ctnnoet in dsnnieedcg oredr

You have to sort the inner content of every word of a string in descending order.
The inner content is the content of a word without first and the last char.

Some examples:
```
"sort the inner content in descending order" -> "srot the inner ctonnet in dsnnieedcg oredr"
"wait for me" -> "wiat for me"
"this kata is easy" -> "tihs ktaa is esay"
```

The string will never be null and will never be empty.
It will contain only lowercase-letters and whitespaces.

In C++ the string is always 0-terminated.

# My answer
```typescript
export function sortTheInnerContent(words:string):string
{
  const arr = words.split(' ')
  const wordsArr = arr.map((word: string) => {
    if (word.length === 1) {
      return word
    }
    const wordArr: string[] = word.split('')
    const copiedWordArr = wordArr.concat()
    copiedWordArr.shift()
    copiedWordArr.pop()
    const sortedArr = copiedWordArr.sort((a: string, b: string) => {
      if (a > b) {
        return -1
      } else {
        return 1
      }
    })
    sortedArr.unshift(wordArr[0])
    sortedArr.push(wordArr[wordArr.length - 1])
    return sortedArr.join('')
  })
  return wordsArr.join(' ')
}
```