# jq(1)

## Filter

    jq '.'                                       # pretty format
    jq '.foo'                                    # return value of key 'foo'
    jq '.foo, .bar'                              # return value of key 'foo' and key 'bar'
    jq '.[]'                                     # return all of the elements of an array
    jq '.foo[0]'                                 # return first element of foo-array

## Operators & Functions

    jq 'keys'                                    # return keys in an array
    jq '.foo | keys'                             # return keys of key foo
    jq '.foo | length'                           # return number of elements

# jq examples

  Search/Filter in JSON array:

    npx sfcc-ci code:list --json | jq '.data[] | select(.active == true) | .id'
    cat data.json | jq '.[] | select(.name == "Foo") | .name'                               # all 'Foo'
    cat data.json | jq '.[] | select(.name == "Foo" or .name == "Bar" | not) | .name'       # all except 'Foo' and 'Bar'

  Append JSON key:

    cat file.json | jq '. += {"foo": "bar"}'

  Delete a key:

    cat file.json | jq 'del(.foo)'               # delete 'foo' key from first level
    cat file.json | jq 'del(..|.foo?)'           # delete 'foo' keys from all levels

  Replace value of JSON key:

    cat file.json | jq '(.foo) |= "baz"'         # replace values of `foo`

  String Interpolation

    jq '. | "value: \(.foo) \(.bar)"'

  Decode JWT token

    cat jwt.txt | jq -R 'split(".") | .[1] | @base64d | fromjson'

  Print all Values of a Key except if the Key is null:

    cat file.json | jq '.[]  | select(.Key != null) | .Key'
