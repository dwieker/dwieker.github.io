---
layout: post
title: Desktop Chess App/Chess Engine
---

![Ouput](https://github.com/dwieker/dwieker.github.io/blob/master/images/chessApp.png?raw=true)


![GIF](https://github.com/dwieker/ChessApp/blob/master/gif/out.gif?raw=true)

 

The history of chess engines is pretty interesting. Modern computers can easily defeat any human player -- even
grandmasters -- but there's been many attempts at different algorithms and techniques before that was true. With the help of online chess AI resources, a friend and I decided to attempt our own chess engine.

### Board Representation
There's multiple ways to represent the state of a chess board, each with pros and cons. You can store a 2-d array of pieces (8x8 -- the size of a chess board), or a 1d list of pieces, where each piece stores its current position. There's also [bitboards](https://chessprogramming.wikispaces.com/Bitboards), which is considered to be one of the fastest implementations (but also difficult). We went with something called the ["0x88" representation](https://chessprogramming.wikispaces.com/0x88) because it was relatively easy to implement and was also very fast (you can quickly calculate whether a piece is near an edge, or on a diagonal, or in rank with another piece, etc.)

### Game Rules
Next, we had to program the internal game logic. We made a java class for each chess piece and encoded all the rules inside of a master Board class that calculates possible moves, searches for checkmate, etc. 

Random fact: there's apparently a move called the [en passant](https://www.chess.com/chessopedia/view/en-passant), which I had absolutely no idea existed. Who knew.

To test the accuracy of the game rules, you can recursively generate every possible move sequence and count the number of board states at each depth. The numbers should match already determined counts. If they don't match, your moving rules are incorrect -- at some point the board is making illegal moves or not seeing possible moves. 

### Output
There's a standard style of chess engine: [UCI](https://en.wikipedia.org/wiki/Universal_Chess_Interface). We wrote our code to abide by this standard. You setup internal board states with a string representing the state of the board, and send commands to the chess engine through standard input, such as "move a2a3" (moves piece on a2 to a3). The chess engine then responds with its decision to standard output.

### AI
The cool part. We used an algorithm called "alpha-beta",  which is essentially an optimized version of the ["mini-max" algorithm](https://en.wikipedia.org/wiki/Minimax). The short explanation: the algorthim recursively iterates through every possible future sequence of moves and evaluates the state of the board at the end of each sequence, ingnoring sequences that lead to unfaforable outcomes and further investigating sequences that look promising. Board state had to be quantified, which I did with a combination of piece count (more pieces = better) and piece positioning (knights should be in the center, bishops should have a line of sight across the board, etc.). We also added logic that forced the alpha-beta algorithm to search deeper when there is a lot of action (if a piece is taken, don't stop looking; search moves after to see if the piece might be captured back immeditately, for example)

### Graphical Interface
I made a GUI using the java swing libraries so we could easily see our engine play. The GUI can load any UCI compatible engine and any set of piece images. 

Work in progress! [Feel free to steal it](https://github.com/dwieker/ChessApp)

Credit to Jesenia Garcia-Rovetta for helping with this project
garciarovetta@gmail.com 
