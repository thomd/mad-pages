# Standard Markdown

  Paragraphs

    a paragraph

    another paragraph [two spaces]
    with a linebreak

  Headline

    # h1 header
    ## h2 header
    ###### h6 header

    h1 header
    =========

    h2 header
    ---------

  Blockquote

    > a blockquote
    >
    > > a nested blockquote

  List

    * unordered item 1
    + unordered item 2
    - unordered item 3

    1. ordered item 1
    2. ordered item 2

  Codeblock

        a line of code indented by at least 4 spaces or 1 tab
        another line of code

  Emphasis

    \*italics\* or \_italics\_

    \*\*bold\*\* or \_\_bold\_\_

  Inline Code

    some \`inline code\`

  Link

    an [example link](http://example.com/) and another [example link][id]

    [id]: http://example.com/ "optional page title"

  Image

    ![alt text](/path/to/img.png)

    ![alt text][id]

    [id]: /path/to/img.png

# JIRA Markdown

see [Text Formatting Notation Help](https://jira.atlassian.com/secure/WikiRendererHelpAction.jspa?section=all)

  Headline

    h1. headline h1
    h2. headline h2
    ...
    h6. headline h6

  Emphasis

    \*\*bold\*\*

    \_italics\_

    -~strikethrough-~

    +underlined+

  Table

    || head 1 || head 2 || head 3 ||
    | row 1 | row 2 | row 3 |
    | row 1 | row 2 | row 3 |

    || || head 1 || head 2 ||
    || head 2 | row 1 | row 2 |
    || head 3 | row 1 | row 1 |

  Image

    !image.png|width=200,thumbnail!

  Code

    this is {{inline code}} within a paragraph

    {code:javascript}
    // block of code
    var foo;
    {code}

    \```javascript
    // block of code
    var foo;
    \```

  Quote

    bq. a single line quote

    > Blockquote: Foo Bar Baz!
    
    {quote}
    multiline quote
    multiline quote
    {quote}

  Panel

    {panel:title=My Title}
    Info panel
    {panel}

    {panel:bgColor=#e3fcef}
    **Success panel**
    {panel}

    {panel:title=Error Lists|bgColor=#ffebe6}
    1. Error
    2. Error
    {panel}

  Link

    On [this|http://example.com] page.

# GitHub Markdown

  Task List

    - [x] foo
    - [ ] bar
    - [ ] baz

  Footnotes

    This is foo[^1] and bar[^2] and baz.

    [^1]: foo footnote

    [^2]: bar footnote

# Azure DevOps Wiki Markdown

  Image

    ![Image alt text](/media/markdown-guidance/image.png)             # absolute path to azure git
    ![Image alt text](./image.png)                                    # relative upload path
    ![Image alt text](./image.png =500x200)                           # scale to 500x200
    ![Image alt text](./image.png =500x)                              # scale to width=500 and keep aspect-ratio
