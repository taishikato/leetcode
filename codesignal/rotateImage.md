https://app.codesignal.com/interview-practice/task/5A8jwLGcEpTPyyjTB

```javascript
/* Basic idea:
 * Walk on the top-left quarter (TL), and move elements clockwise:
 * TL -> TR -> BR -> BL -> TL
 */
function rotateImage(a) {
    let x, y, tmp,
        l = a.length;
        
    for (y = 0; y < l / 2; y++) {
        for (x = y; x < l - y - 1; x++) {
            tmp = a[y][x];
            a[y][x] = a[l - x - 1][y];
            a[l - x - 1][y] = a[l - y - 1][l - x - 1];
            a[l - y - 1][l - x - 1] = a[x][l - y - 1];
            a[x][l - y - 1] = tmp;
        }
    }
    return a;
}
```
