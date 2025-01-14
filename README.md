**Requirements**
1) Chess Board will consists of 64 blocks. i.e 32 White, 32 Black in 8x8 square
2) Game is played between 2 players
3) Player can start a game or join a game
4) White Player must start the game and each player will make move alternatively
5) Each player has 16 pieces. 1 King, 1 Queen, 2 Bishop, 2 Knight, 2 Rook, 8 Pawn
6) Moves will be as per international standards, System will validate all the moves
7) Game ends if White wins, or Black wins, or Stalemate, or Draw
8) Players can save the game in between.

**Assumptions**
1) Player 1 is white
2) Each block has a address or index.
3) System will declare the winner
4) System will maintain the moves and logs of the game
5) Player cannot rollback their moves

**Player can**
1) Start a game
2) Join a game
3) Make a move
4) Save the game
5) resign/cancel the game

**System will**
1) Save the 'move' logs
2) Validate the move
3) Declare the winner
4) Setup the game

**Classes**
1) Board
2) Block
3) Piece
4) Game
5) Move
6) Player
7) Game Status ENUM

1) Board
    initialize() - void
    reset() - void

2) Block
   x, y - int
   label - String
   assignLabel - void
   getPiece() - Piece
   setPiece() - Piece

3) Piece
    isWhite - boolean
    killed - boolean
    canMove(Board, Block, Block) - boolean
   1) King
      castlingDone - boolean
      canMove(Board, Block, Block) - boolean
   2) Queen
      canMove(Board, Block, Block) - boolean
   3) Bishop
      canMove(Board, Block, Block) - boolean
   4) Knight
      canMove(Board, Block, Block) - boolean
   5) Rook
      canMove(Board, Block, Block) - boolean
   6) Pawn
      canMove(Board, Block, Block) - boolean

4) Game
   isWhiteTurn - boolean true
   start()
   makeMove()
   displayWinner()
   STATUS - ENUM(ACTIVE, SAVED, WHITEWIN, BLACKWIN, STALEMATE)

5) Move
   startBlock - Block
   endBlock - Block
   isValid()

6) Player
   name - String
   join(Game);