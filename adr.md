Architectural decision records capture important architectural decisions along with its context and consequences.

# adr(1)

`adr` has a visible history, meaning old/deprecated records are not hidden or removed, but marked as old/deprecated.

List Records

    adr list
    adr generate toc -p doc/adr/ | pbcopy                # genrate TOC in markdown to be used in README.md
    adr generate graph | dot -T png -o adr.png           # generate dependenncy graph
    adr-graph                                            # generate dependenncy graph

Create Record

    adr new \<decision>                                   # create new ADR record  
    adr new -s \<ref> \<superceded decision>               # with ref links "Supercedes ..." and "Superceded by ..." 
    adr new -l \<ref:link:reverse-link> \<decision>        # with ref links "link ..." and "reverse-link ..."
    adr link \<source> Uses \<target> "Used by"            # link source and target with links "Uses ..." and "Used by ..."

  A record id `\<ref>` can be `0001` or `1`.

## Examples

    adr new "Use relational database"                     // record 1: decision to use a relational database
    adr new -s 1 "Use Git as database"                    // record 2: decision to supercede a relational database in favor of git
    adr new -l 2:Extends:"Extended by" "use Github"       // record 3: decision to store data on github

    adr new "Use React for frontend"                      // record 4: decision to use React
    adr new "Use Tailwind CSS"                            // record 5: decision to use Tailwind
    adr link 4 Uses 5 "Used by"                           // link record 4 with 5
