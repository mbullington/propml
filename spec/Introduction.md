# Introduction

As previously stated, PropML is a markup language for documents. You can use it
to define node structures, like HTML. You can also use it as a DSL, in the
category of something like JSX.

```
head {
  title(text = "Test Page")
  script(type = text/javascript, src = main.js)
}
body {
  div@header {
    h1(text = "Test Page")
    hr
    h2(text = "Subtext")
  }
}
```

*PropML can act as, but is not limited to being, an HTML preprocessor.*
