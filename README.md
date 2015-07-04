# propml
Language specification for PropML, a sane alternative to XML and JSON for document markup.

(really super rough draft, pretty much a glorified gist for now)

```
# node declaration, properties are defined with parameters
# after the node name

# if node has no children, brackets may be omitted

test01(a = 1)

test02 {
}

test03(b = 21) {
}

# all are valid node declarations

# strings are defined by the character "
# ' is invalid
# any Unicode char can be prefixed with \u

test04(a = "a b c")

# if the string matches the regex [A-Za-z0-9_-]+
# then string commas can be omitted

test05(a = abc)

# multi-line strings are connotated by three commas on
# each side of the string

# if a string takes up multiple lines but does not have
# three commas, an error is not thrown
# the string will simply be flattened

# newline is determined by \n

# Hello\nWorld!
test06(a = """
  Hello
  World!
""")

# HelloWorld!
test07(a = "
  Hello
  World!
")

# arrays work simply like this
# brackets with an array of values
# seperated by values

test08(a = [1, 2, 3, a, b, c])

# map syntax is an opening and closing bracket
# map syntax also follows the same syntax as
# property syntax

test09(a = {a = 1, b = 2, c = 3})

# here is an example of what a PropML file might
# look like

test1 {
  test2(
    a = a,
    b = 2,
    c = true)
    
  test3(d = [1, 2, 3, a, b, c]) {
    test4(e = {a = a, b = 2, c = true})
  }
}
```
