# pup(1)

Display Functions

    pup 'text{}'                                      # print all text from selected nodes and children in depth first order
    pup 'attr{attrkey}'                               # print values of all attributes with a given key from all selected nodes
    pup 'json{}'                                      # print HTML as JSON

Examples

    cat index.html | pup                              # print formatted html to tty
    cat index.html | pup --color                      # print colorful formatted html to tty

    cat index.html | pup 'title'                      # filter by tag
    cat index.html | pup 'ul.items'                   # filter by class-attribute
    cat index.html | pup 'a[href*="foo"]'             # filter by attribute
    cat index.html | pup 'a attr{href}'               # filter URLs of all links

    cat index.html | pup 'script text{}'              # inline scripts
    cat index.html | pup 'script attr{src}'           # external script links
