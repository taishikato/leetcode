# Question

## Sum of Digits / Digital Root
https://www.codewars.com/kata/541c8630095125aba6000c00

In this kata, you must create a `digital root` function.

A digital root is the recursive sum of all the digits in a number. Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. This is only applicable to the natural numbers.

Here's how it works:

```javascript
digitalRoot(16)
=> 1 + 6
=> 7

digitalRoot(942)
=> 9 + 4 + 2
=> 15 ...
=> 1 + 5
=> 6

digitalRoot(132189)
=> 1 + 3 + 2 + 1 + 8 + 9
=> 24 ...
=> 2 + 4
=> 6

digitalRoot(493193)
=> 4 + 9 + 3 + 1 + 9 + 3
=> 29 ...
=> 2 + 9
=> 11 ...
=> 1 + 1
=> 2
```

# My answer

```typescript
export const digitalRoot = (n:number):number => {
  const recursiveSum = (n2: number): number => {
    const numberArr: string[] = [...String(n2)]
    const sum = numberArr.reduce((acc: number, current: string): number => {
      acc += Number(current)  
      return acc
    }, 0)
    if (String(sum).length === 1) {
      return sum
    }
    return recursiveSum(sum)
  }
  
  return recursiveSum(n)
};
```