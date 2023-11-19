# NEOVIM FROM SCRATCH 
notes from this series: https://www.youtube.com/watch?v=ctH-a-1eUME&list=PLhoH5vyxr6Qq41NFL4GvhFp-WLd5xzIzZ

the config of neovim is specify in a file called init.lua 
you CAN just WRITE EVERYTHING INSIDE THIS FILE 
BUT you can also do some SEPARATION OF CONCERNS into OTHER FILE 
then ultimately INCLUDE to the init.lua 

HOW TO CALL VIM COMMANDS WITHOUT LOSING THE MOVEMENT BINDINGS ?? 
    -> : ctrl + f 
    or q: 

HOW TO INSTALL LAZY.NVIM plugin manager 
LIST OF PLUGINS TO USE, with configs 
    + Telescope: fuzzy finder 
    + Rose-pine: colorscheme
    + Tree-sitter: fast language parsing, SYNTAX HIGHLIGHTING
    -> I don't think i need it:  
        + Harpoon: fast file navigation, with file marking and stuff 
        + undotree: have a tree of undo, that you can go back in time, kinda 
        + vim-fugitive: git intergration

    + lsp zero nvim:  Lsp 

    TODO: LSP thingy still NOT WORKING 

NOTE: 
    =ap -> auto format code 