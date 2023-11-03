# HOW TO FIND A SOLUTION 
notes from this article: https://www.topcoder.com/thrive/articles/How%20To%20Find%20a%20Solution

## Introduction 
    Goals: 
        find solutions using a COLLECTION of common TRAITS/BEHAVIOURS(dac diem) that problems with similar solutions often have.  
        -> learn HOW to OBSERVE those traits/behaviours

    Type of Solution with their problem traits/behaviours: 
        + STRAIGHT-FORWARD PROBLEMS that don't require any special technique: (simulation, searching, sorting, etc,...)
            traits: 
                -> just ask you to execute all steps describe in the problem statements. 
                -> just a matter of coding -> not thinking, algorithmic skills  

        + Breadth First Searchs: 
            traits: 
                -> ASK to find the FEWEST number of STEPS/shortest path to REACH a certain ENDPOINT/STATE
                -> offered: 
                    + WAYS OF PASSING from ONE POINT TO ANOTHER (with given COST)
                    + MxN table, represents: mazes, maps, cities, ... 
            vd1: 
            SmartWordToy – SRM 233 Div 1:
            A word composed of four Latin lowercase letters is given. With a single button click you can change any letter to the previous or next letter in alphabetical order (for example ‘c’ can be changed to ‘b’ or ‘d’). The alphabet is circular, thus ‘a’ can become ‘z’, and ‘z’ can become ‘a’ with one click.

            A collection of constraints is also given, each defining a set of forbidden words. A constraint is composed of 4 strings of letters. A word is forbidden if each of its characters is contained in corresponding string of a single constraint, i.e. first letter is contained in the first string, the second letter – in the second string, and so on. For example, the constraint “lf a tc e” defines the words “late”, “fate”, “lace” and “face”.

            You should find the minimum number of button presses required to reach the word finish from the word start without passing through forbidden words, or return -1 if this is not possible.

            -> Abstract/Restate the problem: 
                given a ordered set of 4 lowercase letters in the alphabet. 
                each of the letter in the set can change to the previous or next letter in the alphabet table. 
                    vd: 'a' can change to 'z' or 'b'
                        'c' can change to 'b' or 'd'

                given a set of forbidden string: 
                    a forbidden string composed of 4 strings of letters
                    vd: "lf a tc e"
                a word is forbidden 
                    if letter_i of word is contained in substring_i of forbidden string

                    vd: forbidden string: "lf a tc e"
                    vd: the word: "fate", "late", "lace", "face" is forbidden  

                -> find the minimum number of change (in total) needed for the "starting word" to convert into the "finish word"
                    return -1 if not possible 

            -> Extracted traits (from the Abstract problem): 
                + ask: find the mininum
                + offered: 
                    + way to move from 1 state/letter to the other (with given cost = 1 (click), all cost is equal)
                        move back and forth in alphabetical order -> no direction
                        z <-> a <-> b
                    + MxN table: with 4 letters by 26 letters 

                -> Should use BFS 

            vd2: 
            CaptureThemAll – SRM 207 Div 2 (3rd problem):
            Harry is playing a chess game. 
            He has one knight, and his opponent Joe has a queen and a rook. 
            Find the minimum number of steps that Harry’s knight has to jump so that it captures both the queen and the rook.

            -> Abstract/Restate the problem (should use only mathematical objects (vd: set)): 
                set A {ngua}
                set B {hau, xe}
                -> find the min steps to move 
                    from "ngua" to "hau" then "xe" 
                    or
                    from "ngua" to "xe" then "hau"

            -> Extracted traits (extract from the Abstracted/Restated problem): 
                + ask: 
                + offer: 
                    + way to move from 1 state/position to the other (cost = 1)
                        back and forth, no direction

                    + MxN table: the graph of all the points to move from "ngua" to the other one 

                -> Should use BFS 

        + Flood fill: 
            ....  

        + Brute force and BackTracking:  
            traits: 
                -> 
                -> 

        + Dynamic Programming: 
            traits: 
                -> 
                -> 

        + Linear Programming (Simple algorithm): 
            traits: 
                -> 
                -> 