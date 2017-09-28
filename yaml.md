
# JSON

    {
      "key": "value",
      "array": [
        "value1",
        "value2"
      ],
      "map": {
        "key1": "value1",
        "key1": "value1"
      },
      "array2": [
        {
          "key1": "value1",
          "key2": "value2"
        }
      ]
    }

# YAML

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

