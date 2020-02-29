# Question
https://www.codewars.com/kata/587731fda577b3d1b0001196

Write simple .camelCase method (`camel_case` function in PHP, `CamelCase` in C# or `camelCase` in Java) for strings. All words must have their first letter capitalized without spaces.

For instance:

```javascript
camelCase("hello case"); // => "HelloCase"
camelCase("camel case word"); // => "CamelCaseWord"
```

# My answer
```typescript
export function camelCase(str: string): string {
  const arr = str.split(' ')
  const bigArr = arr.map((word: string) => {
    const length = word.length
    return `${word.slice(0, 1).toUpperCase()}${word.slice(1, length)}`
  })
  return bigArr.join('')
}
```