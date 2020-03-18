# JavaScript Funk

- I created this repo to share (and also note down) the funky things I learned about JavaScript in my coding journey :)

---

##### 1. String Concatenation & Plus Operator (+)

In JavaScript, we all know that we can add numbers and strings together with the plus operator.

```javascript
5 + 9
// Expected result: 14

'Hello' + ' ' + 'World'
// Expected result: 'Hello World'
```

But what will happen if we add operands that are __not__ 'numbers' or 'strings' together?

```javascript
[1,2] + 8
// Expected result: '1,28'. 
// I actually got asked this question while I mentored at the JavaScript beginners’ workshop at MusesCodeJS. 
// At that time, I was exepcting an error as I thought it's not possible to add two values with different data types. 
// However, the implicit type coercion actually kicks in here.

[1, 2] + [3, 4]
// Expected result: '1,23,4'
```

The reason being that the '+' will convert these two arrays into strings before it adds them up.

Then, what would you expect to happen for the following example?

```javascript
[1,2] + [5,6,7][1,2]
// Expected result: '1,27' (what???)
```
Let's try to break this down! 

First of all, '[5,6,7][1,2]' results in '7' because:

1. [5,6,7] is an array literal of 3 numbers.
2. [1,2] is a [bracket notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors) to access an element of the array [5,6,7].
3. Inside [1,2], there's a [comma operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator) that will evaluate to its right most expression, which is '2' in this case.
4. OK, now let's try to revert it back!
```javascript
[1,2] // will result in [2]

[5,6,7][1,2] // is the same as [5,6,7][2]

[5,6,7][2] // will result in '7' (Remember element '7' is at index postion of '2')

[1,2] + 7 // will result in '1,27' (As explained above, [1,2] will be converted to string with '+' )

```

---

#### References:
- [Why is [1,2] + [3,4] = “1,23,4” in JavaScript?](https://stackoverflow.com/questions/7124884/why-is-1-2-3-4-1-23-4-in-javascript)
- [What is [1,2,3,4][1,2] in javascript](https://stackoverflow.com/questions/43657724/what-is-1-2-3-41-2-in-javascript)


<!-- 
```javascript
```

```javascript
```

```javascript
``` -->

