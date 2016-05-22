---
layout: post
title: Desktop Chess App/Chess Engine
---

![Ouput](https://github.com/dwieker/dwieker.github.io/blob/master/images/chessApp.png?raw=true)

 

The history of chess engines is pretty interesting. Modern computers can easily defeat any human player -- even
grandmasters -- but there's been many attempts at different algorithms and techniques before that was true. With the help of online chess AI resources, I decided to attempt my own chess engine to learn more about the game (and see if it could beat any of my friends.)

### Board Representation
There's multiple ways to represent the state of a chess board, each with pros and cons. You can store a 2-d array of pieces (8x8 -- the size of a chess board), or a 1d list of pieces, where each piece stores its current position. There's also [bitboards](https://chessprogramming.wikispaces.com/Bitboards). I went with something called the ["0x88" representation](https://chessprogramming.wikispaces.com/0x88) because it was relatively easy to implement and very fast (you can quickly calculate whether a piece is near an edge, or on a diagonal, or in rank with another piece, etc.)

### Game Rules
Next, I had to program the internal game logic. I made a java class for each chess piece and encoded all the rules inside of a master Board class that calculates possible moves, searches for checkmate, etc.

### Output
There's a standard style of chess engine: [UCI](https://en.wikipedia.org/wiki/Universal_Chess_Interface). I wrote my code to abide by this standard. You setup internal board states with a string representing the state of the board, and send commands to the chess engine through standard input, such as "move a2a3" (moves piece on a2 to a3). The chess engine then responds with its decision to standard output.

### AI
The cool part. I used an algorithm called "alpha-beta",  which is essentially an optimized version of the ["mini-max" algorithm](https://en.wikipedia.org/wiki/Minimax). The short explanation: the algorthim recursively iterates through every possible future sequence of moves and evaluates the state of the board at the end of each sequence, ingnoring sequences that lead to unfaforable outcomes and further investigating sequences that look promising. Board state had to be quantified, which I did with a combination of piece count (more pieces = better) and piece positioning (knights should be in the center, bishops should have a line of sight across the board, etc.). I also added logic that forced the alpha-beta algorithm to search deeper when there is a lot of action (if a piece is taken, don't stop looking; search moves after to see if the piece might be captured back immeditately, for example)

### Graphical Interface
I made a GUI using the java swing libraries so I could easily see my engine play. The GUI can load any UCI compatible engine and any set of piece images. 

Work in progress! [Feel free to steal it](https://github.com/dwieker/ChessApp)
