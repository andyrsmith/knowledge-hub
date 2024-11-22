# Type Coercion

Since Javascript is a weakly typed language it will try to change the type of a value to match the other value when needed.

An example will be when adding a string to a number
```
"a" + 5  \\This outputs 'a5'

```

## Implict vs explicit 

Explicit coercion is when convert a value to a different type by using a method like Number() or toString().

Implicit is where javascript automatically has to do the conversion.  Like when you use a math operator like + * / -, etc.

## == vs ===

== check if the value is the same and not type.

=== check if value and type is the same

```
'5' == 5 // is true
'5' === 5 // false because one is a string and the other is a number
```