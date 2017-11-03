# Minesweeper

## Background
In the game minesweeper, you are presented with a square grid landscape of cells.  Hidden in some of the cells are ‘mines’.  At every turn, you may select a cell to uncover.  At this point, one of two things will happen:  if there is a mine at that location, it explodes and you lose the game; if there is not a mine at that location, it reveals a number, indicating the number of adjacent cells where there are mines.  If the cell reveals 0, all the surrounding 8 cells are empty of mines.  If the cell reveals 8, all 8 adjacent cells must have mines.  For any value in between, for instance 4,  you know that half of the adjacent cells have mines,  but you cannot be sure by this clue alone which half are dangerous and which half are safe.
The goal of the game is to identify the locations of all the mines (if possible); by collecting clues and information, you
can begin to infer which cells are dangerous and which are safe, and use the safe cells to collect more information.
This process is iterated until, hopefully, all cells are either uncovered, marked as clear, or marked as mined.


## Goal
The  goal  of  this  project  is  to  play  MineSweeper  -  that  is,  a  program  capable  of  sequentially deciding what cells to check, and using the resulting information to direct future action.

## Representation
The board configuration is represented by a 2 D array holding the value 9 in each cell representing that the cell is not yet explored. For the first time computer guesses a random location. If for any computer query the user enters - 2( which is the number that represents a bomb chosen arbitrarily) the game stops. Any value that the user entered if not - 2 is updated in the corresponding location (9 is replaced with that value).

## Inference
The main loop runs until all the locations on the board are cleared. After the first time the
computer will query locations which have less probability of being a bomb location among the
ones available. If the location guessed is known to be have no bombs around it then all the
neighbouring cells around it are explored. If a cell with no bombs is present in the neighborhood
of the previous location then the locations around it are also explored recursively. All the
locations which are already explored( except locations which don’t have a bomb around them)
and not a bomb are checked to see if there any cells that can be unlocked or determined as a
bomb.
If the value of the cell is equal to the number of unexplored cells around it then all are
considered to be bombs. Similarly if the number of bombs around a cell is equal to the cell value
then all the unexplored cells around it be determined as safe. The neighbors of the changed
locations mentioned in the previous sentence are tested to see if the change affected their
positions causing some cells to be unlocked.
If there aren’t any cells that can be queried directly then the locations with are at the intersection
of the neighborhood of two cells are considered and based on the difference between the
values of the 2 cells under consideration cells are either cleared or declared as bombs
For example:

|1| | 3|
|-----|:--------:|---------:|
|1    |TITLE	 |TEXT     |RADIO BUTTON LOOKUP:MR,MRS,MS|SELECT GENDER|


1
A B C
2
Around the cell 2 , A + B + C = 2 and for the cell 1, B +C = 1 solving the two equations will
given that A = 1 i.e there is a bomb in location A. This is implemented using sets in the code, by
finding the intersection of neighbors which gives locations B and C between cells 1 and 2.
Subtracting the sets for 1 and 2 gives (A,B,C) - (B,C) = 2-1 = 1.
There is no explicit knowledge base used in the code except the neighborhood of a given
location is checked to draw inferences about that location. As more and more cells are unlocked
the possible values for locations will decrease.
