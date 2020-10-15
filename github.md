# GitHub Code Search

Search for code based on what language it's written in

    language:	

  Example: 

    sfcc language:go

Match code files with a certain filename

    filename:	

  Example:

    sfcc fileame:package.json


Match code files with a certain file extension

    extension:	

  Example:

    sfcc extension:jsonn

Matches code where search term appears in the file path / file content

    in:path
    in:file

Exclude Operator: Matches repositories that have a word but not another word

    NOT

  Example:

    foo NOT bar

Exclude Qualifier: Matches repositories that have a word but not in an entity

    -

  Example:

    foo -language:css	
