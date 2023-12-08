# TMUX - TERMINAL MULTIPLEXER 

notes from many sources: 
    https://www.youtube.com/watch?v=Yl7NFenTgIo

## Create a session: 
    command: tmux 

## Create a pane: 
    command: 
        ctrl b + % (create a pane on the RIGHT)
        ctrl b + " (create a pane on the BOTTOM)

    -> Switch between pane: 
        ctrl b + <- or -> (left arrow or right arrow)

## Create window: 
    A separate viewport that can contains n pane (Basically like tab in VIM)
    command: ctrl b + c 
    -> Move between window:  
        ctrl b + window_index (vd: 0, 1, 2,...)

## TMUX most powerful feature is SESSION: 
    it store states ... 

    Tmux Session in another abstraction on top of tmux windows
    Basically abstractions goes like this: 
        sessions -> windows -> panes 

    you can: 
        detatch session: 
            command: tmux new -s <name>
        attach session: 
            command: ...  
        create new session with name: 
            command: ... 
        kill session: 
            command: tmux kill-session -t <name> 

## Closing pane, session, window: 
    command: exit  
