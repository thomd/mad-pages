
# UltiSnips

## New Snippets

open editor with 

    :UltiSnipsEdit

create snippet with

    snip \<tab>

## Syntax

`$0` : last Tabstop

`$1` : first Tabstop & Mirror

`${1:defaultText}` : Placeholder (Tabstop with a default text)

`${1/.*/replaceText/g}` : Transformation

`${VISUAL}` or `${VISUAL:defaultText}` : Insert what was visualy selected
