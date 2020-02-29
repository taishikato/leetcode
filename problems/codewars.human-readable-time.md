# Question
https://www.codewars.com/kata/52685f7382004e774f0001f7

Write a function, which takes a non-negative integer (seconds) as input and returns the time in a human-readable format (`HH:MM:SS`)

* `HH` = hours, padded to 2 digits, range: 00 - 99
* `MM` = minutes, padded to 2 digits, range: 00 - 59
* `SS` = seconds, padded to 2 digits, range: 00 - 59

The maximum time never exceeds 359999 (`99:59:59`)

You can find some examples in the test fixtures.

# My answer

```javascript
function humanReadable(seconds) {
  const anHour = 60 * 60
  const aMinute = 60
  let hh = '00'
  let mm = '00'
  let ss = '00'
  let surplusSecond = 0
  if (seconds >= anHour) {
    hh = Math.floor(seconds / anHour)
    surplusSecond = seconds % anHour 
    if (surplusSecond >= aMinute) {
      mm = Math.floor(surplusSecond / aMinute)
      ss = surplusSecond % aMinute
    } else {
      ss = surplusSecond
    }
  } else {
    if (seconds >= aMinute) {
      mm = Math.floor(seconds / aMinute)
      ss = seconds % aMinute
    } else {
      ss = seconds
    }
  }
  
  hh = String(hh)
  if (hh.length < 2) hh = `0${hh}`
  mm = String(mm)
  if (mm.length < 2) mm = `0${mm}`
  ss = String(ss)
  if (ss.length < 2) ss = `0${ss}`
  
  return `${hh}:${mm}:${ss}`
}
```