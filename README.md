# Minesweeper

## Background
In the game minesweeper, you are presented with a square grid landscape of cells.  Hidden in some of the cells are
‘mines’.  At every turn, you may select a cell to uncover.  At this point, one of two things will happen:  if there is a
mine at that location, it explodes and you lose the game; if there is not a mine at that location, it reveals a number,
indicating the number of adjacent cells where there are mines.  If the cell reveals 0, all the surrounding 8 cells are
empty of mines.  If the cell reveals 8, all 8 adjacent cells must have mines.  For any value in between, for instance
4,  you know that half of the adjacent cells have mines,  but you cannot be sure by this clue alone which half are
dangerous and which half are safe.
The goal of the game is to identify the locations of all the mines (if possible); by collecting clues and information, you
can begin to infer which cells are dangerous and which are safe, and use the safe cells to collect more information.
This process is iterated until, hopefully, all cells are either uncovered, marked as clear, or marked as mined.


