# Gomoku

Code C++ for Gomoku Game.

**Key Features of the Program:**

+ Player Turns: The game alternates between two players, where player 1 is 'X' and player 2 is 'O'.

+ Input Format: Players make moves by entering row and column coordinates (e.g., "3a", "5e").

+ Move Validation: The program validates whether a move is valid (i.e., within bounds and on an empty spot).

+ Winning Condition: A player wins when they get exactly 5 consecutive marks either horizontally, vertically, or diagonally.

+ Move History: The game supports a move history feature, where players can go back or forward through the game history using commands.

+ Undo & Redo: Players can undo their last move (go to the previous move) or redo (move forward to the next move).

**Detailed Breakdown:**

Structures and Constants

+ Stone Enum: Represents the possible states of a cell: NA (no move), X, and O.

The board is a 2D array game[15][15] where each element is a Stone enum type. The program uses constants for special characters to draw the board, as well as for commands and other strings.

**Main Gameplay Loop (startGame)**

- The game board is initialized to an empty state (NA).

- Players take turns entering their moves until a player wins (five consecutive stones of their type in a row, column, or diagonal). A player opts to finish the game with "ff" (forced finish). After each valid move, the game checks if the player has won using the hasWon function. If the board is full or the game ends, the program announces the winner.

**Checking for a Win (hasWon)**

- The hasWon function checks whether a player has 5 consecutive stones in a row in any of the four directions (horizontal, vertical, diagonal).

- It avoids counting sequences longer than 5 (they are invalid per the rules) and ensures that the sequence is blocked on both ends by the opponent's pieces.

**Displaying the Board (displayBoardSimple)**

- The board is displayed after every valid move, with 'X' and 'O' showing the current state of the game.

- The displayBoardSimple function prints the board without any additional borders or formatting.

**Handling Move History (displayHistory)**

- The displayHistory function simulates the ability to navigate through the history of moves made in a game.

**The user can:**
- Move to the next move (n).
- Go to the previous move (p).
- Stop the game (s).

**Enhancements and Issues to Address:**

**1. Move Parsing:**
  
- The move input is expected to be in the form "1a", "2b", etc., where the row is a number and the column is a letter.

- The move parsing logic needs a little refinement to handle input properly.

- If the move is invalid or out of bounds, it returns false. When checking the validity of a move in the makeMove function, you might want to add further checks for incorrect input (like checking if the row is too large, or if the letter for columns is beyond 'a' to 'o').

**2. Edge Cases:**

- There should be additional checks in hasWon to ensure that the search only returns a winning condition if exactly 5 stones are aligned, considering blocked ends. Ensure that the row and column indices used in functions like hasWon are calculated properly (adjusting row and column values as needed).

**3. User Interface:**

- The user interface could be enhanced for better playability, such as using better graphics for the board or adding clearer instructions for users to input valid moves.

**4. Move History Parsing:**

- The displayHistory function can be improved by allowing more flexible history formats. For example, if the history contains a mix of 2-character and 3-character moves, the code needs to handle the transition between different move formats correctly.
