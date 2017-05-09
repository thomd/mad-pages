
# emmet vim

    ctrl-y			   # expand in insert mode
    ctrl-y d			   # balance a tag inward
    ctrl-y D			   # balance a tag outward
    ctrl-y m			   # merge selected lines
    ctrl-y j			   # join
    ctrl-y k			   # remove a tag (move cursor inside tag)
    ctrl-y /			   # toggle comment

## Abbreviations

    !                            # html skeleton
    html:5			   # html skeleton
    meta:vp			   # viewport meta tag
    lorem			   # dummy text
    lorem10			   # dummy text with 10 words

    >                            # child
    +                            # sibling
    ^                            # climb-up

    ul>li*5			   # list of 5 empty elements
    ul>li.item-$*5		   # list of 5 empty elements with class "item-x"
    ul>li{item-$$$}*5            # list of 5 elements with text "item-xxx"
    ul>li.item-${item-$$$}*5	   # list of 5 elements with class "item-x" and text "item-xxx"
    ul>li*5>lorem3		   # list of 5 elements with lorem text of three words

    a[href="link$$"]{link$$}*10  # list of 10 anchor links

    h1{headline}+p               # Insert Text
    (.head>h1>p)+(.footer>p)     # Sibling of groups
    .wrap>p>a^p                  # Climb up
    ul.list>.item                # implicit tag
