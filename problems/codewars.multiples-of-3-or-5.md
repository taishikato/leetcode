# Question
https://www.codewars.com/kata/514b92a657cdc65150000006

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in.

> Note: If the number is a multiple of both 3 and 5, only count it once.

# My answer

```javascript
function solution(number){
  const arr = []
  for (let i = 1; i < number; i++) {
    const surplusBy3 = i % 3
    const surplusBy5 = i % 5
    if (surplusBy3 === 0 && surplusBy5 === 0) {
      arr.push(i)
    } else if (surplusBy3 === 0) {
      arr.push(i)
    } else if (surplusBy5 === 0) {
      arr.push(i)
    }
  }
  return arr.reduce((val1, val2) => val1 + val2, 0)
}
```