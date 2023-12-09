# TMUX - TERMINAL MULTIPLEXER 

notes from many sources: 
    https://www.youtube.com/watch?v=Yl7NFenTgIo

## NOTE: Leader: Ctrl b 

## Create a session: 
    command: tmux 

## Create a pane: 
    command: 
        Leader + % (create a pane on the RIGHT)
        Leader + " (create a pane on the BOTTOM)

    -> Switch between pane: 
        Leader + <- or -> (left arrow or right arrow)

    Change different layout: Leader space 

## Create window: 
    A separate viewport that can contains n pane (Basically like tab in VIM)
    command: Leader + c 
    -> Move between window:  
        Leader + window_index (vd: 0, 1, 2,...)

## TMUX most powerful feature is SESSION: 
    it store states ... 

    Tmux Session in another abstraction on top of tmux windows
    Basically abstractions goes like this: 
        sessions -> windows -> panes 

    you can: 
        detatch session: 
            command: tmux new -s <name>
        ATTACH SESSION: 
            command: 
        create new session with name: 
            command: ... 
        kill session: 
            command: tmux kill-session -t <name>    

    Tmux also have command window: 
        Leader : (almost like Vim)
        we can:
            rename window: 
            COMMAND: rename-window <name> 

    Switch back to the previous window:  Leader n

    NOTE: the session exist longer than your terminal 
        -> your terminal closed, the session still there 
        -> just ATTACH to it can everything still there 

## Closing pane, session, window: 
    command: exit  

## MAKE TMUX EVEN BETTER: 
    works good: https://www.youtube.com/watch?v=ceRYL271cao
    looks good: https://www.youtube.com/watch?v=H70lULWJeig
