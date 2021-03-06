# For Loops

The for statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement or a set of statements executed in the loop.

The for loop has the following syntax:

```javascript
for ([initialization]; [condition]; [final-expression]) {  
    code block to be executed                  
}
```

[initialization] is executed before the loop (the code block) starts.

[condition] defines the condition for running the loop (the code block).

[final-expression] is executed each time after the loop (the code block) has been executed.

## Example in Javascript:

```
var ourArray = [];
for (var i = 0; i < 5; i++) {
    ourArray.push(i);
}
```

From the example above, you can read:

[initialization] sets a variable before the loop starts (var i = 0).

[condition] defines the condition for the loop to run (i must be less than 5).

[final-expression] increases a value (i++) each time the code block in the loop has been executed.

## Why we need "for loops"?

For loops is used to loop through a block of code a known number of times. Sometimes it is the computer that knows how many times, not you, but it is still known. Also, check out other loops (While and Do While).
