# tictaktoe

- You need a emu 8086 emulator
- The games started With **X** and Then **O**
- The code check for every input and if it is invalid a message will printed
- Player can't put his symbol on a place already taken


## procedures

>main proc
### This procedure print hello message and draw the game 


>game_loop
### This procedure loops for the games until it is finished 



> readfrom_keyboard
### It takes one character from the user



> check_validaty
#### checks the validaty for the input from readfrom_keyboard and if the input was not between 0 and 9 Then an Error message appear 

>set_value 
### after The validaty The a symbol replace the chosen number  



****
## **Then after repeating The above then a win check start**   

>check first row 
>
>check_secoend_row 
>
>check_third_row

### These Three procedures Checks a single row if there is similar symbols it increase a __win_flag__ by comparing the value of the offset of the each row cells


***

### check columns

>call check_first_column 
>
>call check_secoend_column
> 
>call check_third_column

### These Three procedures Checks a single column if there is similar symbols it increase a __win_flag__ by comparing the value of the offset of the each column cells 
***
### check diagonal
>check_first_diagonal
>
>check_secoend_diagonal

### These Two procedures Checks diagonal if there is similar symbols it increase a __win_flag__ by comparing the value of the offset of the diagonal cells 
***

```
cmp win_flag,2
je print_winer
```

#### And then compare the value of win_flag with 2 


#### if True then it will jump to print_winer wich prints the winner and end the game

***

```
mov win_flag,0
```
#### Reset the win_flag counter

***

>chang_player_symbol
### This changes the symbol of the player if it was (X) Then it will be (O) and so on
***

## Then the game loop ends and if no one won the program will execute the next and exit the game
```
lea dx,no_winner_ms ;; equal
call print
jmp exit
```
***

> print proc
### input
> **The offset in dx** 
### output
> **The string that dx refere to**

***
>set_value proc
### input
> number in hexadecimal
### output
> compare the hexadecimal value with the number of cell which the player entered stored in the **al** if they equal then set the cell with player's symbol
***
>set_n_value 

**Which n from first to ninth and refere to the game cells**

### it uses the offset of the cell then write the symbol of the player on it
***

