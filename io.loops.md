
# while loop

    while(\<condition>, expression)

  Keeps evaluating message until condition return `nil`. 
  Returns the result of the last message evaluated or `nil` if none were evaluated.

    i := 0
    while(i <= 6, i println; i = i + 1)

# for loop

    for(\<counter>, \<start>, \<end>, expression)
    for(\<counter>, \<start>, \<end>, \<optional-step>, expression)

    for(i, 1, 10, write(i, " "))
