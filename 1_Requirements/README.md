# Requirements
## Description
 * Tic-tac-toe in America , also known as noughts and crosses , or Xs and Os in Irish english, is a game for two players, X and O, who take turns marking the spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a diagonal, horizontal, or vertical row is the winner. It is a solved game with a forced draw assuming best play from both players. It is usually played on paper but as the technology evolved, here is it's digital version.

## Research
### Tic-tac-toe Game Features and Benefits
It is often used as a pedagogical tool for teaching the concepts of good sportsmanship and the branch of artificial intelligence that deals with the searching of game trees. It is straightforward to write a computer program to play tic-tac-toe perfectly or to enumerate the 765 essentially different positions (the state space complexity) or the 26,830 possible games up to rotations and reflections (the game tree complexity) on this space. If played optimally by both players, the game always ends in a draw, making tic-tac-toe a futile game.

The game can be generalized to an m,n,k-game in which two players alternate placing stones of their own color on an m×n board, with the goal of getting k of their own color in a row. Tic-tac-toe is the (3,3,3)-game.Harary's generalized tic-tac-toe is an even broader generalization of tic-tac-toe. It can also be generalized as a nd game. Tic-tac-toe is the game where n equals 3 and d equals 2.It can be generalised even further by playing on an arbitrary incidence structure, where rows are lines and cells are points.

## Benefits
Tic-tac-toe Game offers following benefits:

### Good Sportsmanship
Like any game, tic tac toe also teaches a person to accept the defeat as well as ackowledge the win.

### Concentration
It can help to improve a person's concentration as well as strategic thinking

### Developement of Coordination
Tic-tac-toe helps develop coordination, fine motor skills and visual skills.


## Defining Our System

![Description](https://github.com/ArnoldKevinDesouza/Tic-Tac-Toe/blob/main/6_Media/flow.png?raw=true)
### Explanation:
* The game starts giving you three input options(1, 2, 3):
    * 1 means you play using 'X'.
    * 2 means you play using 'O'.
    * 3 means you exit the game.
* The game ends when:
    * It is in a draw situation , i.e, a total of 9 moves have been completed and novody has won.
    * You win.
    * The computer wins.
* The game continues in the beginning if the check for draw is false.
* Then it checks if anyone has won yet.
* If not, then it again checks if it is a draw situation.

# Detail requirements
## High Level Requirements: 
| ID | Description | 
| ----- | ----- | 
| HR01 | User can choose 'X' to play |
| HR02 | User can choose 'O' to play |
| HR03 | User canExit the game |
| HR04 | User can lose|
| HR05 | User can win|
| HR06 | User can end up in a Draw situation|
##  Low level Requirements:
 
| ID | Description | HLR ID |
| ------ | --------- | ------ |
| LR01 | If the user presses '1', he will play with 'X'. | HR01 |
| LR02 | If the user is playing with 'X', he will get the first turn. | HR01 |
| LR03 | If the user presses '2', he willplay with 'O'. | HR02 |
| LR04 | If the user is playing with 'O', he'll get the second turn. | HR02 |
| LR05 | Theone who makes 3 Xs or 3 Os in vertical,horizontal or diagonal row will win | HR03 |
| LR06 | If the total number of moves, i.e., 9 completed and none won ,then it will be a draw. | HR06 |

## SWOT ANALYSIS
![Screenshot (373)](https://user-images.githubusercontent.com/98889318/153358695-c9440b83-c47a-41cd-aa42-ddc63c3d3adc.png)

# 4W&#39;s and 1&#39;H

## Who:
* Anyone can play this game for entertainment.

## What:
* This game is for recreational purposes. 
* Development of strategies can be done as there are many possible outcomes in this game.

## When:
* This game can be played while feeling bored.

## Where:
* A variety of websites make a simple tic tac toe game available.
* Also used in businesses and organizations.


## How:
* It can be implemented in a business strategies. First mover advantage is also there as in any business in the world. In business, it can be a bit more complicated. 

