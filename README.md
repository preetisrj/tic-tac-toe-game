# tic-tac-toe-game
theboard=[' ' ]*10

def printboard(board):
    
    print(board[1]+'|'+board[2]+'|'+board[3])
    print('------')
    print(board[4]+'|'+board[5]+'|'+board[6])
    print('------')
    print(board[7]+'|'+board[8]+'|'+board[9])
   
   

printboard(theboard)
player1=input('enter your name player1:  ')
player2= input('enter your name player2:  ')
    



def win_check(turn,board):
   
    return ((board[7]==turn and board[8]==turn and board[9]== turn) or 
    (board[4]==turn and board[5]==turn and board[6]== turn) or
    (board[7]==turn and board[5]==turn and board[3]== turn) or
    (board[9]==turn and board[5]==turn and board[1]== turn) or
    (board[9]==turn and board[6]==turn and board[3]== turn) or
    (board[8]==turn and board[5]==turn and board[2]== turn) or
    (board[7]==turn and board[4]==turn and board[1]== turn) )

def space_check(board, move):
    
    return board[move] ==' '

def full_board_check(board):
    for i in range(1,10):
        if space_check(board,i):
            return False
    return True

import random
def count_check():
    if random.randint(0,1)==0:
        return 'player2'
    else:
        return 'player1'   

def start_game():
    turn='x'
    count=count_check()
    for i in range(9):
        if count=='player1':
            printboard(theboard)
            print(player1+' '+turn+ '  on the board?')
            move = int(input())
            theboard[move]=turn
        
            if win_check(turn,theboard):
                printboard(theboard)
            
                print(player1+' you win')
                break
            else:
                if full_board_check(theboard):
                    printboard(theboard)
                    print('draw match')
                    break
                else:
                    count='player2'
        else:
            
            printboard(theboard)
            print(player2+' '+turn+ ' on the board?')
            move = int(input())
            theboard[move]=turn
        
            if win_check(turn,theboard):
                printboard(theboard)
            
                print(player2+' you win')
                break
            else:
                if full_board_check(theboard):
                    printboard(theboard)
                    print('draw match')
                    break
                else:
                    count='player1'
            
        if turn=='x':
             turn='o'
        else:
            turn='x'
            
print('do you want to play "yes" enter')
f=input('yes')
if f=='yes':
    start_game()
else:
    print('end')
    

        
