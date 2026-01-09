# jo(1)

## create object

    jo a=                                      # {"a": null}
    jo a=b                                     # {"a": "b"}
    jo a=1                                     # {"a": 1}
    jo a@T                                     # {"a": true}
    jo a@T                                     # {"a": false}

## create array

    seq 1 3 | jo -a                            # [1, 2, 3]
    jo -a 1 2 3                                # [1, 2, 3]
    jo a[]=1 a[]=2 a[]=3                       # {"a": [1, 2, 3]}
    jo -a $(jo a=0) $(jo b=1)                  # [{"a":0},{"b":1}]

## create nested object

    jo a[b]=1                                  # {"a": {"b": 1}}
    jo -d. a.b=1                               # {"a": {"b": 1}}
    jo a=$(jo b=1)                             # {"a": {"b": 1}}

## extend objects

    jo a=b | jo -f - n=1                       # {"a": "b", "n": 1} - append

## insert from file

    echo test > test.txt | jo a=@test.txt      # {"a": "test"} - insert from stdin
    echo test > test.txt | jo a=%test.txt      # {"a": "dGVzdAo="} - insert from stdin encoded as base64
    echo test | jo a=@-                        # {"a": "test"}
    echo test | jo a=%-                        # {"a": "dGVzdAo="}
