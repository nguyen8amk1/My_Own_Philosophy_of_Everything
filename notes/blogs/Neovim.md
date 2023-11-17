# INTRODUCTION TO NEOVIM PLUGIN 
notes from these blogs: 
https://vonheikemen.github.io/devlog/tools/neovim-plugins-to-get-started/
https://vonheikemen.github.io/devlog/tools/build-your-first-lua-config-for-neovim/

Configuration Language: Lua
## How to write Neovim configuration 
configuration file called: init.lua 
Config File LOCATION: 
    depends on: 
        + Operating system 
        + Environment variables 

    -> We use a COMMAND for NeoVim GENERATE it 
        :call mkdir(stdpath("config"), "p") 
            -> CREATE a FOLDER CONTAINS CONFIGURATION FILE 
        stdpath("config") = the standard path for config folder 
        at first the file didn't exist -> 
            CREATE it using this COMMAND: :exe "edit" stdpath("config") . "/init.lua"

    1 single command to do all steps of config file creation: 
        nvim --headless -c 'call mkdir(stdpath("config"), "p") | exe "edit" stdpath("config") . "/init.lua" | write | quit'

    $MYVIMRC: the PATH for init.lua file is store in the variable 

Editor setting: 
    use GLOBAL VARIABLE/MODULE: vim  
        -> it has a lot of property we can use 
        vd: 
        opt - option
            -> contains 351 options of Neovim 
            vim.opt.option_name = value
            Option has a SCOPE:
                + global 
                + current window 
                + file 
            Useful options: 
                + vim.opt.number // show number line 
                + vim.opt.mouse // enable the use of mouse 
                    can enable for different modes(insert, control) 
                        to enable for all modes: 'a'
                + vim.opt.ignorecase // ignore case when executing search 
                + vim.opt.smartcase // ignore uppercase letter unless the search string has uppercase letter 
                + vim.opt.hlsearch  // 
                + vim.opt.wrap  // 
                + vim.opt.breakindent  // preserve the identation of a virtual line (can only see when wrap is enable) 
                + vim.opt.tabstop // the amount of space a tab should occupy 
                + vim.opt.shiftwidth // the shift width >> should be = tabstop
                + vim.opt.expandtab // decide whether or not the TAB should be CONVERTED to SPACE 

        keymap - keymapping key - action: 
            vim.keymap.set({mode}, {lhs}, {rhs}, {opts})
                {mode}:
                    + n: normal mode
                    + i: insert mode
                    + x: visual mode
                    ... 
                {lhs}: the key we want to bind 
                {rhs}: the action we want to execute
                {opts}: options

                <leader> key: special SEQUENCE of keybinding
                    -> we can put it in the {lhs} paramter of vim.keymap.set 
                    -> DEFINE a <leader> = vim.g.mapleader = sequenceString

            Useful keybindings: 
                Default behaviour of Neovim DOESN'T take into ACCOUNT the SYSTEM CLIPBOARD 
                the 'y' key copy the text into INTERNAL REGISTER.  

                Copy to clipboard: 
                    vim.keymap.set({'n', 'x'}, 'gy', '"+y')
                Paste from clipboard: 
                    vim.keymap.set({'n', 'x'}, 'gp', '"+p')

    To apply the config use command: :source 

## How to install plugin 
How to install plugin manually: 
    -> download them in a SPECIFIC FOLDER 
    -> Neovim take care of the rest 
    for more information: please read the blog

Using Plugin Manager: 
    vd: lazy.nvim 
        pag.nvim

    Lazy.nvim: 


Popular Plugins: 
colorscheme: 
    + Tokyonight 
    + onedark.vim 
    + darkplus.nvim 
    + monokai.nvim 
    + 