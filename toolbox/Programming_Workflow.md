# MY PROGRAMMING WORKFLOW 
THE CONTROL GRANULARITY GET'S FINER THE FURTHER DOWN.
THIS WORKFLOW IS A COPY FROM PRIMAGEAN: 
    https://www.youtube.com/watch?v=bdumjiHabhQ
THIS IS WORKFLOW "CHEATSHEET" :V 

## WINDOW MANAGER - I3 
    ... 
    -> Basically separate the viewport for different tasks 
    which you can alter between with a single keystroke
    rather than alt-tabbing all the time. 
    vd: alt-1 for browsing, alt-2 for work

    -> it's all ways stay that same way,
    everything will be way faster when you work systematically

    -> Use for different "GUI purpose" ?? 
    -> Better words: Dividing your Desktop Environment into workspaces 

    Can: 
        Config the thing so that when you boot the machine up, 
        everything you need will be just in place  
        All the workspace is just right there :v 

    good videos: 
        https://www.youtube.com/watch?v=XQcCywaD4y4
    ... 

    Workspace mapping: 
        1. entertainment browsing 
        2. work browsing  
        3. work terminal 
        4. Git Desktop ?? 

        5. My slack ?? 
        6. Ultility window 

    Problem: 
        Can't use alt arrow for history traversal any more (in chrome)
        -> since the Alt key is already occupied  
        -> It's great sacrifies anyway 

## TERMINAL MULTIPLEXER - TMUX
    ...
    -> still not understand very well :v 

    -> allow closing the terminal without killing the working sessions
        vd: nodejs server is running, code working,...  
        -> just reattach the tmux with session and everything will be fine.

    Tmux session would be really good for web development: 
        since there are so many services that you have to work simutanously 

    good videos: 
        https://www.youtube.com/watch?v=DzNmUNvnB04
        https://www.youtube.com/watch?v=-B5VDp50daI
            -> https://www.youtube.com/watch?v=ceRYL271cao

    For detail: [TMUX](../toolbox/tmux.md)
    
    Nice features to use: 
        Panes/Windows 
        Sessions: 
        Configuration: 

    Config: 
        location: ~/.tmux.conf 
        set Leader key to Ctrl w: set -g prefix C-w
        move through pane like vim: setw -g mode-keys vi 
            -> can use "Leader h,j,k,l" to move through panes 
            i don't know why but mine didn't work :))

    Key bindings: 
        NOTE: Leader: Ctrl b, (originally) 
            after config: Leader: Ctrl w
        Create a pane: 
            -> Leader + % (create a pane on the RIGHT)
            -> Leader + " (create a pane on the BOTTOM)

        Change different PANE LAYOUT: 
            -> Leader space  
        Move between panes: Leader <-, ->, up_arrow, down_arrow
        Change the position of your current pane: Leader } 

        Create window: Leader c 
        Move to the previous window: Leader n 
        Move between windows: Leader <window_index> 

        Detatch session:  Leader d (still keep tmux running in the background)

        LIST ALL: 
            + SESSIONs
                -> Leader s  
                and choose which session you would want to use: 
                -> use arrow key or j, k  and enter 

            + WINDOWs:  
                -> Leader w 
                and choose which window you would want to use: 
                -> use arrow key or j, k and enter 
                

    Terminal commands: 
        List all sessions: tmux list-sessions, or tmux ls 
        Kill a session: tmux kill-session -t <name> 
        Attach to previous session: tmux attach-session 

    Tmux internal commands: (move to this state by hitting "Leader :", almost like vim)
        Change window name: rename-window <name>  
        Change session name: rename-session <name> 
        

## TEXT EDITOR - NEOVIM 
THE SETUP AND WORKFLOW THAT I COMFORTABLE WITH 
...

Font: 
    Nerdfont Hack ?? (i haven't test this yet :v)

Plugin:
    ... 
    Commenter: ?? 
    Snippet: ?? 
    LSP: ?? 
    Tabline: ?? 
    File system tree: Neotree
    Fuzzy finder: Telescope
        ripgrep: need gripgrep package to do the grepping 
    Main file markers: Harpoon: 
    FILE SYSTEM EDITING like text: Oil.nvim:

Key bindings: 
    ... 
    go back to the i-1 in the cursor position history: ctrl o 
    go back to the i in the cursor position history: 
    go to the next ','(any character though): f , 
    go to the end of the function body: ??  
    TOGGLE between the current and previous pane/split: ctrl w (2 times)
        ->** Very nice to go back to the neotree when you on the right most pane. 
    Move between panes: ctrl w h or ctrl w l
    Split the tab window in half (vertically):  :vs

    buffers related things?? 
    registers releated things?? 


## TERMINAL EMULATOR: 
    currently still using the standard Gnome   
