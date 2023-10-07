# Checkers-Game
# Chess Game Solver

## Problem Definition

The problem at hand is the game of chess, played on an 8x8 square board with 24 pieces in two colors (12 pieces for each player). Pieces can move diagonally, and points are scored when a piece can jump over an opponent's piece, provided there is an empty square behind it. The jumping moves have several conditions:
- If there are multiple opponent pieces in a row, we must jump over them consecutively in a single turn.
- When a player's piece reaches the last row of the opponent's side, it becomes a "king," gaining the ability to move backward as well as forward.
- The game concludes when one player has no remaining pieces, resulting in a win, loss, or draw (+1, -1, 0, respectively).

## Algorithm Used

We employ the minimax algorithm to solve this chess game. In each turn, the player must evaluate all possible moves and select the best move according to the minimax algorithm. This algorithm assesses the value of each board position and selects the move that maximizes or minimizes the expected outcome, depending on whether it's the player's turn or the opponent's turn. In cases where multiple moves have the same value, we choose one randomly.

## Evaluation Method

The game's progress is visualized by printing the board after each move. This display shows the positions of the pieces, allowing players to follow the game. At the end of the game, after the last board is displayed, the user is informed of the winner (or a tie in case of a draw) by labeling the player with a +1 as the winner and the other player with -1 as the loser.

## Dataset

The project does not require external datasets as the game is played in real-time.

## Output

The expected output of this project is a functioning chess game interface that displays the game board and allows players to make moves. The game concludes when one player wins, and the result is displayed on the user interface. To enhance the user experience, a graphical user interface (GUI) may be implemented to make the chessboard and pieces more interactive and visually appealing.

Feel free to customize the game interface and functionality as needed to meet your project's requirements. Enjoy playing and solving chess!

##Further explanation for code: 
This project is designed as a GUI application using the pygame library. It consists of several classes to implement a chess-like game. Here's an overview of the key classes and their functions:

Taw Class:

This class is responsible for defining chess pieces and their movements.
It defines the color and size of the pieces.
It handles the movement of pieces based on their valid directions and the dimensions of the game board.
Each piece, when reaching the opposite end of the board, gets a crown symbol (like a king in chess).
The draw and move functions are used to draw and move the pieces accordingly.
Board Class:

This class is one of the central components of the game, responsible for most game-related features.
It initializes and draws the game board, including the placement of colored pieces based on their positions.
Pieces are positioned on the board based on their color and position, taking into account the valid moves according to the traverse_right and traverse_left functions.
The move function handles the actual movement of pieces, ensuring they move to valid positions and updating their positions on the board.
Game Class:

In the __init__ method of this class, the game board is created using the Board class.
The Game class orchestrates the flow of the game, including player turns, checking the validity of moves, and updating the game board.
It manages player turns and checks for valid moves and piece selections.
The game board is updated with the new positions of the pieces based on valid moves.
The ai_move function is called for the computer's turn, and it selects the optimal move using the minimax algorithm.
Throughout the class, functions from the Board class are used to ensure the validity of moves, switch turns, move pieces, and more.
Minimax Function:

This function is used for selecting the best move for the computer player.
It takes the current board state, depth of the search tree, the player (min or max), and the game board.
The minimax function recursively explores possible moves and computes scores for each move.
It utilizes the traverse_right and traverse_left functions to find valid moves for each piece.
Based on the calculated scores, it selects the best move for the AI player (max) or the opponent (min).
The selected move is then displayed on the game screen.
In summary, this project implements a chess-like game where pieces (taws) are moved based on their valid moves, and the computer player uses the minimax algorithm to make its moves. The game logic and board management are handled through classes and functions, ensuring a smooth and interactive gaming experience.
