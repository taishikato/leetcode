# Question
https://www.codewars.com/kata/5656b6906de340bd1b0000ac

Take 2 strings `s1` and `s2` including only letters from `a` to `z`. Return a new sorted string, the longest possible, containing distinct letters,

* each taken only once - coming from s1 or s2.

**Examples:**

```
a = "xyaabbbccccdefww"
b = "xxxxyyyyabklmopq"
longest(a, b) -> "abcdefklmopqwxy"

a = "abcdefghijklmnopqrstuvwxyz"
longest(a, a) -> "abcdefghijklmnopqrstuvwxyz"
```

# My answer

```typescript
export class G964 {
  public static longest = (s1: string, s2: string): string => {
    const mergedArr = [...s1.split(''), ...s2.split('')]
    const uniqueArr: string[] = []
    mergedArr.forEach((str :string) => {
      if (uniqueArr.indexOf(str) === -1) {
        uniqueArr.push(str)
      }
    })
    
    return uniqueArr.sort((val1: string, val2: string) => {
      if (val1 > val2) {
        return 1
      } else {
        return -1
      }
    }).join('')
  }    
}
```