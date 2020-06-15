https://app.codesignal.com/interview-practice/task/6rE3maCQwrZS3Mm2H/description

## My Answer

This is ok but has more time complexity than `O(l1.length + l2.length)`.

```javascript
const mergeTwoLinkedLists = (l1, l2) => {
    const arr1 = [];
    const arr2 = [];
    let current = null;
    let prev = null;

    while (l1 !== null) {
        arr1.push(l1.value);
        l1 = l1.next;
    }
    while (l2 !== null) {
        arr2.push(l2.value);
        l2 = l2.next;
    }
    const sorted = arr1.concat(arr2).sort((a, b) => a - b);
    while (sorted.length > 0) {
        const val = sorted.pop();
        current = new ListNode(val);
        current.next = prev;
        prev = current;
    }
    return prev;
}
```

## Smart answer

Recursive

```javascript
const mergeTwoLinkedLists = (l1, l2) => {
    if (l1 === null) return l2;
    if (l2 === null) return l1;
    let ret = new ListNode(Math.min(l1.value, l2.value));
    if (l1.value < l2.value) {
        ret.next = mergeTwoLinkedLists(l1.next, l2);
    } else {
        ret.next = mergeTwoLinkedLists(l1, l2.next);
    }
    return ret;
}
```
