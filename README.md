# Named arguments proposal

The problem lies in the fact that current syntax is heavy and not flexible enough. What I mean by the last is it doesn't allow mixing ordered with named arguments. It's heavy because on each invocation we must add additional braces.

What I consider is changing the standard as follows:

```
ArgumentList:
    AssignmentExpression
    PropertyDefinition
    ArgumentList,AssignmentExpression
    ArgumentList,PropertyDefinition
```
Note as `PropertyDefinition` considers `...AssignmentExpression` we have ommited that one from the syntax declaration above.

Which will allow shorthand and more flexible syntax as following:

```javascript
(function (arg0, arg2){})
(
    arg0: 1, //ok passing first argument with value of 1 because `arg0` identifier matches `arg0` parameter
    2, //ok passing the next after the last passed argument (second) with value of 2
)
```

Another more complex example:

```javascript
let arg0 = 2
(function (arg0, arg2){})
(
    arg0, //ok passing first argument with value of 1
    2, //ok passing the next after the last passed argument (second) with value of 2
)
```

There should be added text that will assign to `arg0` if it's part of the function parameters but if not pass it as the next ordered argument.
