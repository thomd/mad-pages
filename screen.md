# screen(1)

Set escape key to `ctrl-b`:

    echo "escape ^BB" > ~/.screenrc

Start a new screen session

    screen 
    screen -S <name>

Detach screen session and open again

    ctrl-b d
    screen -ls
    screen -r

Create a new Window and switch in between

    ctrl-b c
    ctrl-b b

List of Windows

    ctrl-b "

Create new Region and switch to new Region

    ctrl-b S
    ctrl-b tab
    ctrl-b c
