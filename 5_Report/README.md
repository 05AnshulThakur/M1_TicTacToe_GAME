# Requirements
## Description
 * Tic-tac-toe in America , also known as noughts and crosses , or Xs and Os in Irish english, is a game for two players, X and O, who take turns marking the spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a diagonal, horizontal, or vertical row is the winner. It is a solved game with a forced draw assuming best play from both players. It is usually played on paper but as the technology evolved, here is it's digital version.

## Research
### Tic-tac-toe Game Features 
Tic-tac-toe is played on a three-by-three grid by two players, who alternately place the marks X and O in one of the nine spaces in the grid.
Because of the simplicity of tic-tac-toe, it is often used as a pedagogical tool for teaching the concepts of good sportsmanship and the branch of artificial intelligence that deals with the searching of game trees.

## Benefits
Tic-tac-toe Game offers following benefits:

### Good Sportsmanship
Like any game, tic tac toe also teaches a person to accept the defeat as well as ackowledge the win.

### Concentration
It can help to improve a person's concentration as well as strategic thinking

### Developement of Coordination
Tic-tac-toe helps develop coordination.


## Flow Chart
![Screenshot (374)](https://user-images.githubusercontent.com/98889318/153367238-25872bd0-bd7a-4829-8196-7f8cb831627e.png)


### Explanation:
* The game starts giving you three input options(1, 2, 3):
    * 1 means you are playing with'X'.
    * 2 means you are playing with 'O'.
    * 3 means you exit the game.
* The game ends when:
    * User wins.
    * The computer wins.
    * It is in a draw situation , i.e, a total of 9 moves have been completed and none won.
* The game continues in the beginning if the check for draw is false.
* Then it checks if anyone has won yet.
* If not, then it again checks if it is a draw situation.

# Detailed requirements
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
# Design

### Structural Diagram

![Structural Diagram](https://user-images.githubusercontent.com/98889318/153370356-1285daa6-506e-4120-91bc-278eb22ee954.png)

### Usecase Diagram

![Architecture](https://github.com/ArnoldKevinDesouza/Tic-Tac-Toe/blob/main/6_Media/structural%20HL.png?raw=true)

### Flow Chart

![Screenshot (374)](https://user-images.githubusercontent.com/98889318/153370644-96e6bd13-0aae-4c00-9566-836037377fa9.png)

#include "game_operations.h"

int board[10] = {2,2,2,2,2,2,2,2,2,2};
int turn = 1,flag = 0;
int player,comp;

void menu();
void go(int n);
void start_game();

void draw_board();
void player_first();
void put_X_O(char ch,int pos);
COORD coord= {0,0}; // this is global variable
//center of axis is set to the top left cornor of the screen
void gotoxy(int x,int y)
{
    coord.X=x;
    coord.Y=y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),coord);
}


void main()
{
    system("cls");
    menu();
    getch();

}

void menu()
{
    int choice;
    system("cls");
    printf("\n--------MENU--------");
    printf("\n1 : Play with X (first turn) ");
    printf("\n2 : Play with O (second turn) ");
    printf("\n3 : Exit");
    printf("\nEnter your choice:>");
    scanf("%d",&choice);
    turn = 1;
    switch (choice)
    {
    case 1:
        player = 1;
        comp = 0;
        player_first();
        break;
    case 2:
        player = 0;
        comp = 1;
        start_game();
        break;
    case 3:
        exit(1);
    default:
        menu();
    }
}

int make2()
{
    if(board[5] == 2)
        return 5;
    if(board[2] == 2)
        return 2;
    if(board[4] == 2)
        return 4;
    if(board[6] == 2)
        return 6;
    if(board[8] == 2)
        return 8;
    return 0;
}

int make4()
{
    if(board[1] == 2)
        return 1;
    if(board[3] == 2)
        return 3;
    if(board[7] == 2)
        return 7;
    if(board[9] == 2)
        return 9;
    return 0;
}

int posswin(int p)
{
// p==1 then X   p==0  then  O
    int i;
    int check_val,pos;

    if(p == 1)
        check_val = 18;
    else
        check_val = 50;

    i = 1;
    while(i<=9)//row check
    {
        if(board[i] * board[i+1] * board[i+2] == check_val)
        {
            if(board[i] == 2)
                return i;
            if(board[i+1] == 2)
                return i+1;
            if(board[i+2] == 2)
                return i+2;
        }
        i+=3;
    }

    i = 1;
    while(i<=3)//column check
    {
        if(board[i] * board[i+3] * board[i+6] == check_val)
        {
            if(board[i] == 2)
                return i;
            if(board[i+3] == 2)
                return i+3;
            if(board[i+6] == 2)
                return i+6;
        }
        i++;
    }

    if(board[1] * board[5] * board[9] == check_val)
    {
        if(board[1] == 2)
            return 1;
        if(board[5] == 2)
            return 5;
        if(board[9] == 2)
            return 9;
    }

    if(board[3] * board[5] * board[7] == check_val)
    {
        if(board[3] == 2)
            return 3;
        if(board[5] == 2)
            return 5;
        if(board[7] == 2)
            return 7;
    }
    return 0;
}

void go(int n)
{
    if(turn % 2)
        board[n] = 3;
    else
        board[n] = 5;
    turn++;
}

void player_first()
{
    int pos;

    check_draw( turn);
    draw_board();
    gotoxy(30,18);

    printf("'1' denotes the top left box, '5' denotes the centre and so on.\n ");
    printf("Your Turn :> ");
    scanf("%d",&pos);

    if(board[pos] != 2)
        player_first();

    if(pos == posswin(player))
    {
        go(pos);
        draw_board();
        gotoxy(30,20);
        //textcolor(128+RED);
        printf("Player Wins");
        getch();
        exit(0);
    }

    go(pos);
    draw_board();
    start_game();
}

void start_game()
{
// p==1 then X   p==0  then  O
    if(posswin(comp))
    {
        go(posswin(comp));
        flag = 1;
    }
    else if(posswin(player))
        go(posswin(player));
    else if(make2())
        go(make2());
    else
        go(make4());
    draw_board();

    if(flag)
    {
        gotoxy(30,20);
        //textcolor(128+RED);
        printf("Computer wins");
        getch();
    }
    else
        player_first();
}

//deleted check_draw



void draw_board()
{
    int j;

    for(j=9; j<17; j++)
    {
        gotoxy(35,j);
        printf("|       |");
    }
    gotoxy(28,11);
    printf("-----------------------");
    gotoxy(28,14);
    printf("-----------------------");

    for(j=1; j<10; j++)
    {
        if(board[j] == 3)
            put_X_O('X',j);
        else if(board[j] == 5)
            put_X_O('O',j);
    }
}

void put_X_O(char ch,int pos)
{
    int m;
    int x = 31, y = 10;

    m = pos;

    if(m > 3)
    {
        while(m > 3)
        {
            y += 3;
            m -= 3;
        }
    }
    if(pos % 3 == 0)
        x += 16;
    else
    {
        pos %= 3;
        pos--;
        while(pos)
        {
            x+=8;
            pos--;
        }
    }
    gotoxy(x,y);
    printf("%c",ch);
}
