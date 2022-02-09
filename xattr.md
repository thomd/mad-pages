# xattr(1)

OSX shows extended attributes using an additional symbol `@` at the permissions table:

    ls -l@

## Attributes

* `com.apple.quarantine`: the quarantine flags are set when an agent (browser, mail client etc) saves a file to your machine. This is responsible for the warning that appears when you first try to open an application that was downloaded from the internet.
* `com.apple.metadata:kMDItemWhereFroms`: Describes where the file was obtained from. Show in a readable format via mdls -name kMDItemWhereFroms FILE

## Examples

    xattr FILE                                  # list extended attributes of FILE
    xattr *                                     # list extended attributes of all files
    xattr -p com.apple.quarantine FILE          # print value associated with the given attribute
    xattr -c FILE                               # remove all attributes including their associated values
    xattr -d com.apple.quarantine FILE          # remove given attribute and associated value
    xattr -w foo bar FILE                       # write given attribute and associated value
