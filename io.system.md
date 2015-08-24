
# System

methods related to the IoVM

  call system and redirect `stdout` and `stderr` to `tmp` files, 
  return object with `exitStatus`, `stdout` and `stderr` slots:

    System runCommand("ls -al") stdout

  return the path of io installation:

    System ioPath
