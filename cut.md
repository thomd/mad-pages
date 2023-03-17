# cut(1)

    echo foo,bar,baz | cut -d , -f 2                   # bar
    echo foo,bar,baz | cut -d , -f 1,3                 # foo,baz

    echo "database" | cut -c 1-4                       # data
    echo "database" | cut -c 5-8                       # base
    echo "database" | cut -c 1,5                       # db
