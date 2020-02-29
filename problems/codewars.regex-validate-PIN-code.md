# Question
https://www.codewars.com/kata/55f8a9c06c018a0d6e000132

ATM machines allow 4 or 6 digit PIN codes and PIN codes cannot contain anything but exactly 4 digits or exactly 6 digits.

If the function is passed a valid PIN string, return true, else return false.

eg:

```
validatePIN("1234") === true
validatePIN("12345") === false
validatePIN("a234") === false
```

# My answer

```typescript
export class Kata {
  static validatePin(pin: string): boolean {
    if (pin.length !== 4 && pin.length !== 6) return false
    const arr = pin.split('')
    let flg = true
    for (let i = 0; i < arr.length; i++) {
      if (!arr[i].match(/[0-9]/)) {
        flg = false
        break
      }
    }
    return flg
  }
}
```