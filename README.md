java c
ENGG1110 Problem Solving by Programming
2024-2025   Term 1
Project
Due Date: 2024/12/06 (Fri) 23:59


1.   Introduction
Candy Crush is a popular match-three puzzle game in   the   world, originally released in
2012   for Facebook and later adapted   for mobile platforms.
In   the basic gameplay,   the gameboard consists of a grid   filled   with   various   types of candies, each represented by different shapes and colors.   The player’s goal is to create   matches of three or more identical candies by swapping adjacent one. When a match is   made,   the matched candies are cleared   from   the gameboard, and new candies   will   fall      down   to   fill the empty spaces.   This sometimes leads   to “chain reactions”,   where new matches are automatically created as the board refills.

In   this project,   you   will develop a Candy Crush game using   the C programming   language.   The project is structured in   two phases: Part I focuses on implementing   the   basic   version of   the game,   while Part II builds upon   the   first part by adding advanced features and additional gameplay mechanics.You   are   required   to   complete   the   given   source   code   main.c   without   modifying   any   existing   code   (except   otherwise   specified)   or   introducing   new   libraries.   Marks   will   be   deducted   from every modification.




2.   Program Flow
Part   I

Part   II
   


3.   Suggested Project Schedule
Part   I (60%)
   
Week 10
InitGameBoard(), printGameBoard()
Week 11
AskForSwap()- Input/Validation, swap()
Week 12
FindAndRemoveMatch(), isGameOver()
Part II   (40%)
   
Week 13/14
File I/O, applyGravity, fillEmpty(),Cascade
Week 14
Cascade
4.   Sample Runs for Part I
The   following shows several examples of inputs and   the resulting candy clearings. User   inputs are indicated by bold, highlighted underlined   text.   The matches found by   the function are in red   font.=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | @ | * | # | * |1| @ | @ | * | # | # | % |2| # | % | % | @ | % | * |3| % | * | @ | # | * | @ |4| # | * | @ | % | % | @ |5| % | @ | # | * | % | % |Enter the coordinate (row, column) of the candy:5 2Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):LVertical Match found at column 2!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | @ | * | # | * |1| @ | @ | * | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |5| % | # | | * | % | % |=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | @ | * | # | * |1| @ | @ | * | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |5| % | # | | * | % | % |Enter the coordinate (row, column) of the candy:0 2Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):DHorizontal Match found at row 1!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |

5| % | # | | * | % | % |=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |5| % | # | | * | % | % |Enter the coordinate (row, column) of the candy:0 0Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):LMove Out of Bound.Please try again.=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |5| % | # | | * | % | % |Enter the coordinate (row, column) of the candy:1 2Empty Cell Selected.Please try again.=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | % | % | @ |5| % | # | | * | % | % |Enter the coordinate (row, column) of the candy:4 5Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):DHorizontal Match found at row 4!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |



4| # | * | | | | |5| % | # | | * | % | @ |=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | % | % | @ | % | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |Enter the coordinate (row, column) of the candy:2 3Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):RHorizontal Match found at row 2!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | | | | @ | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |=====New Round:=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | * | * | # | * |1| | | | # | # | % |2| # | | | | @ | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |Enter the coordinate (row, column) of the candy:0 4Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):RHorizontal Match found at row 0!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | | | | # |1| | | | # | # | % |2| # | | | | @ | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |=====New Round:=====



| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | | | | # |1| | | | # | # | % |2| # | | | | @ | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |Enter the coordinate (row, column) of the candy:1 5Enter the direction to swap (U for Up, D for Down, L for Left, Rfor Right):UHorizontal Match found at row 1!=====| 0 | 1 | 2 | 3 | 4 | 5 |0| # | % | | | | % |1| | | | | | |2| # | | | | @ | * |3| % | * | | # | * | @ |4| # | * | | | | |5| % | # | | * | % | @ |Game Over! No more possible moves.




5.   Detailed Program Design Flow   – Part I
In   this project,you are required   to   follow exactly   the output   format specified. Using   other output   formats   will   jeopardize   your mark.
This program   will
1.      Read and initialize the game board  代 写ENGG1110 Problem Solving by Programming 2024-2025 Term 1Statistics
代做程序编程语言 from source
2.      Display   the game board
3.      Allow   the player   to select a candy   to swap
a.      The player can only swap   two candies at a   time
b.    The player will choose a candy by entering   the coordinates (row, column)
c.      The player   will also input a direction (U   for Up, D for Down, L   for Left, R   for
Right)   to specify   where to swap   the selected candy.
4.      Find and remove matches
a.      After each swap, check   for matches of three or more identical candies in   a row or column.
b.      If a match is   found, display a message indicating   the match’s location,   remove   the matched candies, and update   the game board.
5.      Check   for a game-over condition
a.      Check if no further matches are possible on   the gameboard.
b.      If   the board has no possible moves left, display   the message and end the   game.
5.1.                   Header   files, Functions, and   Variable Declarations
At    the    beginning    of      the      main.c   file,      we      include      two      headers,            and
.
No other header   files or library are allowed in   the project.
We   define   several    macros    after   the    header    line.    Macros    are    identifiers    defined    by   #define,   which are replaced by   their   value before compilation.   The   first   two are H   and   W.
#define H   6      //   height
#define W   6      // widthH   is the height of the game board, while W   is its width. Therefore, our Candy Crush game   board is a 6x6 square. In our   test cases,   we do not have any   test cases   with   varying board   size.   You may   try it if   you are interested.Each cell on the game   board stores a candy, with different types of candies represented   by   numbers.   To   assist   in   converting   these   numbers   into   their   corresponding   candy   representations,   the   following global   variable is provided.
char candies[]   =   {'*',   '#',   '@',   '%'};


No other global   variables are permitted.   All   variables   you define must be   declared   within   functions and passed as parameters or return   values as necessary. Violations of   this rule will result   in   a deduction of   marks.
Also,   there are a number of helper   functions declared in   the project.   You can add new   functions   to aid   your   work, but   you CANNOT modify   (function signatures   –   function            names, return type, parameters), or delete   the given   functions.
5.2.                     Main Function
The main   function is given   to control   the game flow.
There are some local   variables already declared   for   you.   You can declare   your own local   variables   for   your use.
Variables
Usages
int   board[H][W]
Stores   the candies on   the game board.
The main   function controls   the   gameplay as   follows:
1.      Call initGameBoard()   to load   the initial game board.
2.      Enter   the main game loop.   The loop should continue until   the game is over. Here   are   the   tasks in   the loop.
a.      The loop should start by printing   five equal signs (=====) as a separator   for each round, as   follows:
=====
New   Round:
b.    Then, call printGameBoard()to display   the current game board.
=====|   0   |   1   |   2   |   3   |   4   |   5   |   0|   #   |   %   |   @   |   *   |   #   |   *   |   1|   @   |   @   |   *   |   #   |   #   |   %   |   2|   #   |   %   |   %   |   @   |   %   |   *   |   3|   %   |   *   |   @   |   #   |   *   |   @   |   4|   #   |   *   |   @   |   %   |   %   |   @   |   5|   %   |   @   |   #   |   *   |   %   |   %   |
c.      Call askForSwap() to execute   the swapping logic. If   the askForSwap()      returns zero (0), indicating   the swapping is unsuccessful. In   this case,   print   the   following error message:
Please   try again.\n
d.      Call isGameOver()to check if any moves are possible.   If no   valid moves         remain, display a game over message and exit   the game loop. In   this case,   print   the   following error message:
Game Over! No more   possible   moves.\n
5.3.                     Initializing Game BoardThe main()   function   will   first call   the initGameBoard()function,   which initializes   the board[]   array   for the later gameplay. In Part I, the content of   the array should be read   from another hard-coded arrays   – board_samples[].
5.4.                     Print Game BoardThe   given   printGameBoard()   is   useful   throughout   the   program   to   show   the   current   game board status to the user.   You are required to implement this function and print the   game   board on the screen   based on the following format, where   ␣   represents   a   space   character   that should appear as an actual space in   the program output.First, print a line of five equal signs (=====) as a separator. Then, display the game board   with   row   and   column   numbers   labeled.   Each   cell   should   be   separated   by   spaces   and   vertical bars   to clearly distinguish   rows and columns.
=====␣␣|␣0␣|␣1␣|␣2␣|␣3␣|␣4␣|␣5␣|   ␣0|␣#␣|␣%␣|␣@␣|␣*␣|␣#␣|␣*␣|   ␣1|␣@␣|␣@␣|␣*␣|␣#␣|␣#␣|␣%␣|   ␣2|␣#␣|␣%␣|␣%␣|␣@␣|␣%␣|␣*␣|   ␣3|␣%␣|␣*␣|␣@␣|␣#␣|␣*␣|␣@␣|   ␣4|␣#␣|␣*␣|␣@␣|␣%␣|␣%␣|␣@␣|   ␣5|␣%␣|␣@␣|␣#␣|␣*␣|␣%␣|␣%␣|
There are   two   types of elements displayed on   the grid:
•          Candies: Use the candies[] character array   to convert   the numerical   values stored in board[][] into the corresponding candy symbols.
•          Empty Space: Display   the space character (' '),   which is stored in   board[][]   as   ASCII 32 (space).
It is crucial   that   your output   format   follows   the example exactly, including   the number   of spaces and any other formatting details, as   the program   will be graded using an autograder.   Any deviation in   the   format could result in a loss of marks.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
