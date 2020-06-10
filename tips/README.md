### `new` operator

When you use `new` operator, constructor method set a new object as a value of `this`.
And returns a object(`this`) without `return`.

### Clone object
```javascript
const obj = { hoge: 'yeah', fuga: 'yes' }

// Old
const clone = obj.assign({}, obj)

// ES2018
const clone = { ...obj }
```

### Convert string to an array
```javascript
const name = 'takato'

// Traditional
const arr = name.split('')

// New
const arr = [ ...name ]
```

### Get the minimum value
```javascript
const arr = [3, 10, 6, 7]
Math.min(...arr) // 3
```

### Convert number to string
```javascript
const n = 123

const str = n.toString() // "123"
String(num); // "123"
num + ''; // "123"
'' + num; // "123"
```

### Truncating decimal
```javascript
Math.floor(10/3) // 3
```

### Convert binary
```javascript
parseInt('0101001', 2) // 41
```

## Array related
### Delete a specific element(in place)
[Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
```javascript
const items = ['リンゴ', 'メロン', 'イチゴ', 'スイカ'];
// delete the element of index 0
items.splice(0, 1);
console.log( items ); // ["メロン", "イチゴ", "スイカ"]
```

### Merge arrays
```javascript
const arr1 = ['apple', 'orange']
const arr2 = ['monkey', 'bird']

const merged = arr1.concat(arr2)
console.log(merged) // [ 'apple', 'orange', 'monkey', 'bird' ]
```

### Generate an unique array from string
```javascript
const str = 'abc'
const str2 = 'ade'
console.log([...str, ...str2]) // [ 'a', 'b', 'c', 'a', 'd', 'e' ]
console.log(new Set([...str, ...str2])) // Set { 'a', 'b', 'c', 'd', 'e' } Setオブジェクトにすると重複が消される
console.log(Array.from(new Set([...str, ...str2]))) // [ 'a', 'b', 'c', 'd', 'e' ] SetオブジェクトをArrayへ
```

### Find the first and last occurrence of the specified value

```javascript
const items = ['apple', 'melon', 'cherry', 'watermelon', 'cherry'];

const first = items.indexOf('cherry');
const last = items.lastIndexOf('cherry');
```

## String related

### Extract some parts from string
[String.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
```javascript
const str = 'The quick brown fox jumps over the lazy dog.'
const spliced = str.splice(3, 15) // or substring() https://qiita.com/littlekbt/items/4a47f485391b6b45d96c
```

### Search a specified value
[String.prototype.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
```javascript
const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';

const searchTerm = 'dog';
const indexOfFirst = paragraph.indexOf(searchTerm);
```
