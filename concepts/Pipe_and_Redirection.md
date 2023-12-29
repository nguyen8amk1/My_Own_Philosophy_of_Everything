# PIPE and REDIRECTION 
notes from video: https://www.youtube.com/watch?v=-Z5tCri-QlI&ab_channel=tutoriaLinux

## Basic idea of linux: 
    -> the OUTPUT of 1 program can become  
       the INPUT of another program

## Every process have 3 CHANNELS: 
    Each has a NUMBER ATTACH to it: 

    STDIN (0): input from somewhere, 
        vd: file, keyboard, network,... 

    STDOUT (1): output to somewhere, 
        vd: file, shell, network,... 

    STDERR (2):  output error to somewhere
        vd: file, shell, network,... 

    The number attached to the channel is use for redirection: 
        vd: 
            echo "ditme" 1> somefile 

        the number stand before the '>' or ">>"
        
## Redirection: 
    -> The act of changing the STDIN, STDOUT, STDERR of a program 
        vd: the default STDOUT is shell -> we can CHANGE the STDOUT from SHELL to FILE 

    Output redirection:  >, >>
    Input redirection:  <, << 

## Piping: 
    -> Output of a program is the input of another command
    Hooks the STDOUT (1) or a program to the STDIN (0) of another program 

## Redirection vs Piping 
    Purpose: 
        Piping: 
            -> Transfers output of one command to another as input.
        Redirection: 
            -> CHANGES THE FLOW of input/output/error streams.

    Connection: 
        Piping: 
            -> CONNECTS STDOUT of one command to STDIN of another.

        Redirection: 
            -> REDIRECTS STDOUT or STDERR to a file or device.

    Multiple commands: 
        Piping: 
            -> Can chain MULTIPLE COMMANDS together.
        Redirection: 
            -> Typically used with a SINGLE COMMAND.

    Directionality: 
        Piping: 
            -> Unidirectional (STDOUT to STDIN).
                1 ways 
        Redirection: 
            -> Bi-directional (input or output redirection).
                both ways 

    Streams affected: 
        Piping: 
            -> AFFECTS DATA FLOW BETWEEN COMMANDS.

        Redirection: 
            -> Primarily affects input/output/error STREAMS of a SINGLE COMMAND

    -> CONCLUSIONS: 
        Piping: 
            focused on: 
                chaining commands together

        Redirection:
            focused on:
                modify the flow of input/output/error streams for a single command.
                vd: sending input to a file, taking input from a file.
