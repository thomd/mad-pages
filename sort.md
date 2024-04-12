# sort(1)

Options

    -c                # just check if is already sorted
    -u                # reduce identical lines (equal to sort ... | uniq)
    -d                # consider only blanks and alphanumeric characters
    -f                # ignore case
    -i                # ignore not printable chars
    -r                # reverse sort (descending)
    -n                # sort numerical
    -t SEP            # field separator
    -k m,n            # sort on a particular field (start at m, end at n)
    -V                # sort version numbers

Example

    sort -t: -nk3 /etc/passwd | more         # sort passwd file by 3rd field
    sort -rn                                 # sort numerical in reverse order
    sort -nrk2 zipcode                       # sort second column numerical & reverse
    sort -t'|' -k2 zipcode                   # sort a pipe-delimited file
    sort -k2n -k1 zipcode                    # sort second column numerical and first column lexically
    sort a b | uniq > c                      # c is a union b
    sort a b | uniq -d > c                   # c is a intersect b
    sort a b b | uniq -u > c                 # c is set difference a - b

