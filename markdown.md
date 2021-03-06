
# Markdown

Markdown is a lightweight markup language. Readability is emphasized above all else.

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

  Headline

    h1. headline h1
    h2. headline h2
    ...
    h6. headline h6

  Emphasis

    \*bold\*

    \_italics\_

    -strike through-

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

  Quote

    bq. a single line quote

    {quote}
    multiline quote
    multiline quote
    {quote}

  Panel

    {panel:title=My title}
    my panel text
    {panel}

  Link

    On [this|http://example.com] page.
