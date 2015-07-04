# String

String is a value type in PropML.

There are three types of Strings in PropML.

Unicode characters can be expressed by being prefixed with `\u`.

TODO: add information about shorthand for newline, etc

For basic and multi-line strings, if the opening comma is preceded with an `r`,
anything escaped will be parsed as part of the string itself. This is useful
for paths on certain platforms and regular expressions.

## Basic Strings

Basic strings in PropML are wrapped with a double quote on each side of the
string. Single quote characters are not acceptable for defining a basic string.
If a string is wrapped with single quotes, the string should attempt
to be parsed as an identifier string, with errors thrown accordingly.

If a basic string takes up multiple lines, an error should be thrown.

```
test(a = "Hello world! I'm a String!")
```

## Identifier Strings

If a String is an identifier, it can be expressed without being wrapped in
quotes.

```
test(a = HelloWorld!)
```

Unicode characters are not allowed within the context of an identifier string.

Escaped double commas are also not allowed within the context of an identifier
string.

Identifier strings must contain at least one character or symbol (with the
exception of the period), an identifier string with only numbers may not exist.
PropML implementations will parse this with the corresponding number type.

Identifier strings may not equal true or false, PropML implementations will
parse this as type Boolean.

# Multiline Strings

Multiline Strings are wrapped with three double quotes on each side. Like basic
strings, single quote characters are not acceptable for defining a multiline
string. Unlike basic strings, PropML implementations should throw an error if
this happens.

In a multiline string, a double comma does not need to be escaped unless there
is three consecutive commas in a row with no whitespace between them.

A new line created right after the opening commas will be trimmed. A new line
created right before the closing commas will also be trimmed.

How multiline strings are flattened into a single-line string depends on
implementation and platform.

```
test(a = """
  Look, I'm a
  multi
  line
  string!
""")
```
