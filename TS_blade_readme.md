# Blade TS parser

## Required parsers

- php
- html

## Run :TSEditQuery highlights blade

Add the following:

```
(directive) @function
(directive_start) @function
(directive_end) @function
(comment) @comment
((parameter) @include (#set! "priority" 110))
((php_only) @include (#set! "priority" 110))
((bracket_start) @function (#set! "priority" 120))
((bracket_end) @function (#set! "priority" 120))
(keyword) @function
```

## Run: TSEditQuery injections blade

Add the following:

```
((text) @injection.content
    (#not-has-ancestor? @injection.content "envoy")
    (#set! injection.combined)
    (#set! injection.language php))
```
