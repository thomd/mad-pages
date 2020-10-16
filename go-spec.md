# Go Pointer

A pointer is a variable that stores the memory address of another variable.

Go does not support Pointer Arithmetic. You can't add to or subtract from pointers.


    & operator                # get memory address
    \* operator                # access the value stored at an address. This is called dereferencing or indirecting
    \*T                        # pointer type. Here, the \* is not an operator, it is part of a type, hence \*T and T are different types.

  Example

    var age int = 49
    var ptr *int = &age
    var ptr = &age            # type inference
    var value = *ptr          # 49
    *ptr = 50                 # Change value stored in the pointed variable through the pointer

  Create a pointer using the built-in new() function:

    ptr := new(int)           # create pointer to an int type
    *ptr = 100
    fmt.Print(*ptr)           # 100

# Go Server

## HTTP/2 Server

    > openssl req -x509 -newkey rsa:4096 -sha256 -nodes -keyout server.key -out server.crt -subj "/CN=localhost" -days 365

    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "foo")
    })
    http.ListenAndServeTLS(":443", "server.crt", "server.key", nil)

    > curl -i -k https://localhost


