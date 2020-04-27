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
    arg0: 1, //ok passing first argument with value of 1
    2, //ok passing the next after the last passed argument (second) with value of 2
)
```
