# jq(1)

## Examples

  Search in JSON array:

    npx sfcc-ci code:list --json | jq '.data[] | select(.active == true) | .id'


## Public JSON APIs

1. https://jsonplaceholder.typicode.com

