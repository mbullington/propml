# Node Structure

In the above HTML-like example, `div@header`, `body`, `title`, and every other
HTML tag on the page is represented as a node. Nodes in PropML are the core of
the language. Nodes can optionally contain attributes, have a type and optional
identifier associated with them, and have children that are also nodes.

Nodes can be defined through the syntax shown below, with brackets symbolizing
the syntax being optional.

```
type[@name][(key = value, ...)][{
  # children here
}]
```

- `type`: Every node in PropML must have a type. Types do not have to be defined
with a schema. In the HTML example, a type represented a HTML tag. `type` is a
subset of an identifier, with the address symbol being reserved.

- `[@name]`: Nodes can also have a name associated with them. If a name is
present, the address symbol is used to divide `name` and `type`. Names do not
have to be unique for each node, but keeping node names unique is good practice,
and may be required depending on how the document is used by an application.
`name` is a subset of an identifier, with the address symbol being reserved,
like `type`.

- `[(key = value, ...)]`: Nodes can also have properties associated with them. If
properties are present, the property list must be enclosed with parenthesis.
Properties are defined using a `key = value` syntax, and are joined by a comma.
Key is always an identifier.

- `[{}]`: Nodes can also have other nodes as children. If a node has children, the
node declaration must be followed by a set of curly brackets. Children must be
defined within the brackets. If the node has no children, these brackets may be
omitted.
