# adr(1)

List Records

    adr list
    adr generate toc -p doc/adr/ | pbcopy                # genrate TOC in markdown to be used in README.md
    adr generate graph | dot -T png -o adr.png           # generate dependenncy graph

Create Record

    adr new \<decision>                                   # create new ADR record  
    adr new -s \<ref> \<superceded decision>               # with ref links "Supercedes ..." and "Superceded by ..." 
    adr new -l \<ref:link:reverse-link> \<decision>        # with ref links "link ..." and "reverse-link ..."
    adr link \<source> uses \<target> "used by"            # link source and target with links "uses ..." and "used by ..."

Example Usage

    adr new use mysql            // record 001: decision to use mysql
    adr new -s 2 use sqlite      // record 002: decision to supercede mysql in favor of sqlite
