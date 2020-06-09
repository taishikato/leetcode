From Codesignal: https://app.codesignal.com/interview-practice/task/pMvymcahZ8dY4g75q

Usually I use `indexOf` when I check that array has a specific value like below.

```typescript
const hasDuplicate = (arr: number[]): number => {
  const seen = [];

  for (let i = 0; i < arr.length; i++) {
    if (seen.indexOf(arr[i]) > -1) return arr[i];
    seen.push(arr[i]);
  }
  return -1
}
```

But the cost of `indexOf` is not that low especially the size of array is big.

## Smart way to solve it

In that case, make an array `seen` of size `a.length` filled with zeros.<br />
When scanning the array and you encounter the number `n`, check if the corresponding element of `seen` is still zero (i.e. `seen[n]` in languages that use a 1-based index, or `seen[n-1]` in languages that use a 0-based index.).<br />
If it the corresponding element is zero, change it to non-zero. If the corresponding element isn't zero, return `n` as you have encountered a duplicate.

**SMART!!**
```typescript
const hasDuplicate = (arr: number[]): number => {
  const seen = Array(arr.length).fill(0);

  for (let i = 0; i < arr.length; i++) {
    if (seen[arr[i] - 1] === 0) {
      seen[arr[i] - 1] = 1;
      continue;
    }
    return arr[i];
  }
  return -1;
}
```

## Or…　Just use Set istead of Array
Because `seen.has()` is `O(1)` time complexity which means it's fast.

```typescript
const hasDuplicate = (arr: number[]): number => {
  const seen = new Set();

  for (let i = 0; i < arr.length; i++) {
    if (seen.has(arr[i])) return arr[i];
    seen.add(arr[i]);
  }
  return -1
}
```

## If you don't need to return the value but boolean… then
```typescript
const hasDuplicate = (arr: number[]): boolean => return arr.length > new Set(arr).size;
```

