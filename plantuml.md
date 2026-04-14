# plantuml(1)

    plantuml --check-syntax diagram.puml              # check syntax only (CI)
    plantuml --gui                                    # launch the graphical user interface

    plantuml diagram.puml                             # generate *.png image of the diagram (default)
    plantuml diagram.puml -f txt                      # generate ASCII art diagrams *.atxt
    plantuml diagram.puml -f utxt                     # generate ASCII art diagrams *.utxt using Unicode characters

    viu diagram.png                                   # view in terminal
    timg diagram.png                                  # view in terminal
