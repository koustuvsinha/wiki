# JavaScript String prototype replace

The `replace()` method returns a new string with some or all matches of a pattern replaced by a replacement. The pattern can be a string or a `RegExp`, and the replacement can be a string or a function to be called for each match.

## Syntax

```javascript
str.replace(regexp|substr, newSubStr|function[, flags])
```

## Parameters

**regexp (pattern)**

A RegExp object. The match is replaced by the return value of parameter #2.

**substr (pattern)**

A String that is to be replaced by newSubStr.

**newSubStr (replacement)**

The String that replaces the substring received from parameter #1\. A number of special replacement patterns are supported; see the "Specifying a string as a parameter" section below.

**function (replacement)**

A function to be invoked to create the new substring (to put in place of the substring received from parameter #1). The arguments supplied to this function are described in the "Specifying a function as a parameter" section below.

[MDN link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) | [MSDN link](https://msdn.microsoft.com/en-us/LIBRary/t0kbytzc%28v=vs.94%29.aspx)

## Returns

A new string with some or all matches of a pattern replaced by a replacement.

## Description

This method does not change the String object it is called on. It simply returns a new string.

To perform a global search and replace, either include the g switch in the regular expression or if the first parameter is a string, include g in the flags parameter.

## Examples

```javascript
var str = 'Twas the night before Xmas...';
var newstr = str.replace(/xmas/i, 'Christmas');
console.log(newstr);  // Twas the night before Christmas...
```

```javascript
function f2c(s1) {
    // Initialize pattern.
    var test = /(\d+(\.\d*)?)F\b/g;

    // Use a function for the replacement.
    var s2 = s1.replace(test,
      function($0,$1,$2)
           { 
           return((($1-32) * 5/9) + "C");
           }
        )
    return s2;
}
document.write(f2c("Water freezes at 32F and boils at 212F."));

// Output: Water freezes at 0C and boils at 100C.
```
