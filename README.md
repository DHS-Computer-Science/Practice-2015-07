# Practice 2015 - 07: Understanding the Internet

## Background
Captain America is trying to work through his list of things to do that he
missed while he was frozen for decades. However, he’s completely stumped by the
popular internet game 2048. He thinks that, if he could see some simulated
games, he might understand it better.

You will simulate a game in which a 4 by 4 grid containing numbered tiles is
manipulated to yield the highest number possible.

The grid will be represented by a 4 by 4 matrix of integers. A value of zero
indicates a blank space (i.e. no tile) at that position. A positive integer
indicates a tile with that integer’s value at that position. No negative
integers are used in this representation.

On one turn of the game, you can tilt the grid in one of four
directions: up (U), down (D), left (L), or right (R). When you tilt the grid,
the grid’s tiles will all slide in the given direction until they either collide
with the edge of the grid or they hit another tile. If a tile collides with
another tile of the same value, then the two tiles will merge, yielding a new
tile numbered with the sum of the two integers. The new tile will be in the
position closer to the edge to which the grid was tilted (if you swipe down,
the new tile will be in the position of the tile closest to the bottom of the
screen). Only tiles present on the board before a move can be combined during
a move. If a tile is created by combination during a move, it cannot be further
combined during the same move.

For example, if we start with the grid:
```
8 2 2 2
4 2 0 0
4 2 0 2
2 2 0 0
```
and tilt it down (D), we will get the grid:
```
0 0 0 0
8 0 0 0
8 4 0 0
2 4 2 4
```
Note that a tile created through a merge cannot merge again on the same turn.
The second column of the previous example demonstrates this rule.


## Description

### Input
The first line of the file will have an integer, n, which is the number of test
cases in this file.

Each test case will contain five lines.

The first four lines of each test case will each contain four space separated
integers. Collectively, they specify the initial grid in the format described
above.The integers are guaranteed to be within the bounds of a 32 bit int.
Likewise, the sums that are generated during each simulation will also be
within the bounds of a 32 bit int. There will always be at least one tile in
the grid.

The fifth line will contain a string (of maximum length 64) of uppercase
characters representing moves (‘D’, ‘U’, ‘L’, or ‘R’). Each character specifies
the direction of a move, as described above. The moves must be executed in
order (e.g. for the string ‘LU’, the initial grid is tilted left, and the
resulting grid is tilted up).

Each test will consist of at most 64 moves.

### Output
The output will have one line per input test case.

Each output line will contain the highest integer value present on a tile in
the grid after the initial grid has undergone all the moves specified in the
input.

The highest value is guaranteed to be within the bounds of a 32 bit int.

## Sample
### Input
```
2
8 2 2 2
4 2 0 0
4 2 0 2
2 2 0 0
DUR
0 3 5 6
6 3 12 0
0 3 0 3
3 0 0 0
LDLUR
```

### Output
```
16
24
```
