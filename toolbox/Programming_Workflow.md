# MY PROGRAMMING WORKFLOW 
THE CONTROL GRANULARITY GET'S FINER THE FURTHER DOWN.
THIS WORKFLOW IS A COPY FROM PRIMAGEAN: 
    https://www.youtube.com/watch?v=bdumjiHabhQ
THIS IS WORKFLOW "CHEATSHEET" :V 

## TODO: 
    FIND FASTER NAVIGATION FOR ALL 3 I3, NVIM, TMUX 
    TMUX: 
        faster window, session navigation 

    CONFIG: 
        COMPLETE THE WORK ENVIRONMENT by Configure all of them. 

        NVIM: 
            -> Finish adding all the lsps and plugin 
            -> FIX THE CLIPBOARD PROBLEM
                some links related to the problem: 
                    https://askubuntu.com/questions/1486871/how-can-i-copy-and-paste-outside-of-neovim

                -> SOLUTION: INSTALL XCLIP or any other clipboard provider and it will magically works 

            -> MAYBE LEARN TO USE GIT ON NVIM AS WELL ?? (optional)
            -> TRY TO USE THE PLUGINS THAT MR.TJ USE: 
                -> https://www.youtube.com/watch?v=39eF0ucBrUU (the beginning of this video is kinda cool)

            -> REMAP CAPSLOCK TO CONTROL (should i ??, optional)
                -> Solution: 
                    Since capslock got processes through OS before it reach NEOVIM  
                    -> you have tackle the program on OS level rather User level 
                    -> Have to remap using i3 -> also means i have to use CAPSLOCK for other stuff as well ?? 
                    

        TMUX: 
            -> Make it look pretty  
            -> PUSH THE CONFIG TO GITHUB, OR AT LEAST TRACK IT  

        I3: 
            -> Make it look better
            -> May be learn some new keybindings ?? 
            -> REMAP CAPSLOCK TO CONTROL
                link: https://www.reddit.com/r/i3wm/comments/2xoo9m/what_is_the_best_way_to_remap_ctrlkey_with/
                current using: setxkbmap -option ctrl:swapcaps


    PUSH ALL THE CONFIG TO GITHUB: 
        TMUX HAVE SOME CONFIG THAT HAVEN'T GET TRACKED
        ALL OF THEM HAVEN'T GET UPDATE FOR A WHILE NOW 

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
        1. entertainment browsing - normally is the only one who makes sound (from watching Youtube)
        2. work browsing - mostly stackoverflow or documents (text-based)
        3. work terminal 
        4. Git Desktop ?? 

        5. My slack ?? 
        6. Ultility window 

    Problem: 
        Can't use alt arrow for history traversal any more (in chrome)
        -> since the Alt key is already occupied  
        -> It's great sacrifies anyway 

        Don't know how to suspend ?? 

    Configuration: 
        ... 

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

    Configuration: 
        ... 
        

## TEXT EDITOR - NEOVIM 
new workflow links:
    text substitution: https://www.youtube.com/watch?v=k_PBlhH-DKk

THE SETUP AND WORKFLOW THAT I COMFORTABLE WITH 
...

1. Configuration: 
    Font: 
        Nerdfont Hack ?? (i haven't test this yet :v)

    Plugin:
        ... 
        ...: flash.nvim ?? 
        Commenter: ?? 
        Snippet: ?? 
        LSP: ?? 
        Tabline: ?? 
        File system tree: Neotree
        Fuzzy finder: Telescope
            ripgrep: need gripgrep package to do the grepping 
        Main file markers: Harpoon: 
        FILE SYSTEM EDITING like text: Oil.nvim:

    Have some keymap as well :v 

Key bindings: 
    ... 
    go back to the i-1 in the cursor position history: ctrl o 

    go back to the i in the cursor position history: ??

    go to the next ','(any character though): f , 
    go to the end of the function body: ??  
    TOGGLE between the current and previous pane/split: ctrl w p
        ->** Very nice to go back to the neotree when you on the right most pane. 
    Move between panes: ctrl w h or ctrl w l
    Split the tab window in half (vertically):  :vs

    buffers related things?? 
    registers releated things?? 
    format the code: wrap the code in visual then =

    when in neotree: 
        show hidden files: shift h

## TERMINAL EMULATOR: 
    currently still using the standard Gnome   


## FINGER PLACEMENT 
    i3: 
        close window: alt shift q
            left hand: 
                thumb - alt
                ring - q
            right hand: 
                pinky - shift 

        workspace navigation: alt <index>
            Primary index: 1, 2, 3
            left hand: 
                thumb - alt 
                index:
                    1 - ring 
                    2 - middle 
                    3 - pointer 
    
    tmux: 
        ... 

## OPERATIONS THAT I USUALLY DO, NOT TYPING RELATED 
    Taking a snapshot, snipping: 
        ...
    Gimping: 
        ...

    Incognito web browsing: 
        ... 
    ... 

## ERRORS THAT I GOT: 

### NVIM: 
    + "file exists, add ! to override".
        -> Might be a TREE-SITTER problem, the link below to see more details
        -> But the problem seems a little bit deeper than that :))
        https://github.com/nvim-treesitter/nvim-treesitter/issues/1004
    + Commentings is not working as expected, it can't uncomment the VSCODE comment style

    + Why the NEOVIM copies directly copy to the system clipboard ?? 
