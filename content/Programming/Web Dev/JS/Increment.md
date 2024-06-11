
Sometimes in niche situations we might get confused between `i++` and `++i`. This example is a simple one to understand the difference between the two.
- **`i++`**: Post-increment operation
- **`++i`**: Pre-increment operation

```js
var i = 0;
var a = i++;  // a is assigned the value of 0, then i is incremented to 1
console.log(a, i);  // Output: 0 1

var j = 0;
var b = ++j;  // j is incremented to 1, then b is assigned the value of 1
console.log(b, j);  // Output: 1 1

```


> [!NOTE] FOR loops
> It doesn't affect FOR loops because the addition is done separately anyways without 
> really affecting the looping
