# YAML Spec

    ---
    key: value
    array:
      - value1
      - value2
    map:
      key1: value1
      key2: value2
    array2:
      -
        key1: value1
        key2: value2

On YAML Syntax:

  Use `whitespace` for indentation, `tab character` is not allowed

  Separate multiple documents within one stream with  `---`

  Strings (scalars) are unquoted, but may be enclosed with `"` or `'`

  Comment with `#`

# yq(1)

    yq validate doc.yml                     # validate valid.yaml
    yq read doc.yml -C                      # print
    yq read doc.yml -jP                     # to JSON and pretty-print
