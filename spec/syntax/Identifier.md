# Identifier

Various times in this document, certain syntax structures will be referred to as
identifiers. An identifier is not an actual type, and is only used for defining
the syntax. The closest comparison to an identifier is a String. An identifier
is a set of letters, numbers, and some symbols.

Identifiers may not:

- Include any symbol reserved for the language syntax. These symbols are
`( ) [ ] { } = , " #`.

- Include spaces.

If an identifier does any of the above, PropML implementations should throw an
error. In most cases, using any of the conventions above will cause your PropML
file to be completely broken.
