# Go Struct

A struct is a **user-defined type** that aggregates related **data** together to form a single unit.

# Function types

Everything in Go is passed **by value** (except Pointers)

# Interface types

An interface is a contract which describes **behaviour** (not data) using method signatures.

Interfaces are **implicit**, hence objects can implement multiple interfaces.

Interfaces are **decoupling** from concrete types.

# Go Pointer

A pointer is a variable that stores the memory address of another variable.

Go does not support Pointer Arithmetic. You can't add to or subtract from pointers.

    & operator                # get memory address
    \* operator                # access the value stored at an address. This is called dereferencing or indirecting
    \*T                        # pointer type. Here, the \* is not an operator, it is part of a type, hence \*T and T are different types.

