Bitwise OR assignment (|=)
==========================

The bitwise OR assignment operator (`|=`) uses the binary representation of both operands, does a bitwise OR operation on them and assigns the result to the variable.

Syntax
------

    Operator: x |= y
    Meaning:  x = x | y

Examples
--------

### Using bitwise OR assignment

    let a = 5;
    a |= 2; // 7
    // 5: 00000000000000000000000000000101
    // 2: 00000000000000000000000000000010
    // -----------------------------------
    // 7: 00000000000000000000000000000111

Specifications
--------------

<table><colgroup><col style="width: 100%" /></colgroup><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><p>ECMAScript Language Specification (ECMAScript)<br />
</p><span class="small">#sec-assignment-operators</span></td></tr></tbody></table>

`Bitwise_OR_assignment`

1

12

1

3

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [Assignment operators in the JS guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment)
-   [Bitwise OR operator](bitwise_or)
-   [Logical OR assignment (`||=`)](logical_or_assignment)

Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR_assignment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR_assignment</a>