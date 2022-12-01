# Tic-Tac-Toe-Full-Game
# Tic Tac Toe Part 1:Single Player Game between Player and Computer. Part 2: Multiplayer Game between Two Players. 
# You are required develop a single and multiplayer player TicToc game with following functionalities 
      # At the start the game should display a welcome message and display following menu 

      # For multiplayer player mode press 1
      # For single player mode press 2
      # To exit press 3

      #If user selects option 1 then following steps should be performed

      # Ask the Player 1 to enter name and choose a symbol i.e. X or O

      # Ask the Player 2 to enter name and then you should display the symbol (other then what has been selected by Player 1) 

      # Toss should be performed between the two Players. Player 1 should toss and Player 2 selects either Head or Tail.

      # Display the grid along with position numbers from 1 to 9. Winner of the toss makes the first move by selecting the box number from the keyboard.

      # The game ends when any of the player successfully forms the winning combination or all the moves have exhausted. 

      # A Message is displayed announcing the winner or draw.

      # At the end of the game players should be asked whether they want to play another game if the player enters Y then the game restarts from step 1 otherwise the game ends. 

      # If user selects option 2 then following steps should be performed

      # Ask the Player 1 to enter name and choose a symbol i.e. X or O

      # Assign other symbol then what has been selected by Player 1 to the computer

      # Toss should be performed between the Player 1 and Computer. Computer should toss and Player 1 selects either Head or Tail.  

      # Display the grid along with position numbers from 1 to 9. Winner of the toss makes the first move by selecting the box number from the keyboard.

      # The game ends when any of the player successfully forms the winning combination or all the moves have exhausted. 

      # A Message is displayed announcing the winner or draw. (Here you have to ensure that computer moves are selected in such a way that either computer wins or # game draws. In no situation Player 1 should win the game.)

      # At the end of the game Player 1 should be asked whether he/she wants to play another game if the player enters Y then the game restarts from step 1 otherwise the game ends. 

      # If user selects option 3 then the game ends

      # Printing main menu of a game.



                                              #Here Is The Code...
                                              #Follow me on Instagram @python.pk


      def find_mode():
          print("                           Please select your desire mode of game       ")
          print("                                      1. Single player            ")
          print("                                      2. Multi player             ")
          print("                                      3. Exit Game                ")
          m = str(input("Enter your choice: "))
          while m != "1" and m != "2" and m != "3":
              m = str(input("Enter your choice again: "))
          return int(m)

      q = find_mode()


      # if player goes for Single Player game!


      while q == 1 or q == 2:
          if q == 1:
              comp = " "
              player = " "

              board = ["-", "-", "-",
                       "-", "-", "-",
                       "-", "-", "-"]
              position = 1
              winner = "NoBody"
              Game_continue = True


              def number_board():
                  print("1", " |", "2", " |", "3")
                  print("___|____|____")
                  print("4", " |", "5", " |", "6")
                  print("___|____|____")
                  print("7", " |", "8", " |", "9")


              def Display_board():
                  print(board[0], " |", board[1], " |", board[2])
                  print("___|____|____")
                  print(board[3], " |", board[4], " |", board[5])
                  print("___|____|____")
                  print(board[6], " |", board[7], " |", board[8])
                  print("                   ")


              def input_Conditions():
                  global position
                  position = input("Enter position 1-9:")
                  while position not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"]:
                      position = input("INVALID INPUT ----Enter position 1-9:")
                  position = int(position) - 1
                  while board[position] == "X" or board[position] == "O" and board[position] not in ["1", "2", "3", "4", "5", "6", "7", "8", "9"] :
                      position = input("INVALID INPUT ----Enter position 1-9:")
                      position = int(position) - 1
                  board[position] = player
                  Display_board()


              def recreate_board():
                  global Game_continue

                  board[0] = "-"
                  board[1] = "-"
                  board[2] = "-"
                  board[3] = "-"
                  board[4] = "-"
                  board[5] = "-"
                  board[6] = "-"
                  board[7] = "-"
                  board[8] = "-"
                  Game_continue = True

      # Condition to make sure sure computer select correct winning mode..

              def bot_cond():
                  global position, user, bot
                  if position == 4:
                      if board[0] == player and board[4] == comp and board[7] == player:
                          board[3] = comp
                      elif board[0] == "-":
                          board[0] = comp
                      elif board[2] == "-":
                          board[2] = comp
                      elif board[6] == "-":
                          board[6] = comp
                      elif board[8] == "-":
                          board[8] = comp
                      elif board[5] == "-":
                          board[5] = comp
                      elif board[1] == "-":
                          board[1] = comp
                      elif board[7] == "-":
                          board[7] = comp
                      elif board[8] == "-":
                          board[8] = comp

                  elif position != 4 and board[4] != player and board[4] != comp:
                      board[4] = comp
                  # Row 1
                  elif board[0] == player and board[1] == player and board[2] == "-":
                      board[2] = comp
                  elif board[0] == player and board[2] == player and board[1] == "-":
                      board[1] = comp
                  elif board[2] == player and board[1] == player and board[0] == "-":
                      board[0] = comp
                  # Row 2
                  elif board[3] == player and board[4] == player and board[5] == "-":
                      board[5] = comp
                  elif board[3] == player and board[5] == player and board[4] == "-":
                      board[4] = comp
                  elif board[5] == player and board[4] == player and board[3] == "-":
                      board[3] = comp
                  # row 3
                  elif board[6] == player and board[7] == player and board[8] == "-":
                      board[8] = comp
                  elif board[6] == player and board[8] == player and board[7] == "-":
                      board[7] = comp
                  elif board[8] == player and board[7] == player and board[6] == "-":
                      board[6] = comp
                  # Column 1
                  elif board[0] == player and board[3] == player and board[6] == "-":
                      board[6] = comp
                  elif board[0] == player and board[6] == player and board[3] == "-":
                      board[3] = comp
                  elif board[6] == player and board[3] == player and board[0] == "-":
                      board[0] = comp
                  # Column 2
                  elif board[1] == player and board[4] == player and board[7] == "-":
                      board[7] = comp
                  elif board[1] == player and board[7] == player and board[4] == "-":
                      board[4] = comp
                  elif board[7] == player and board[4] == player and board[1] == "-":
                      board[1] = comp
                  # Column 3
                  elif board[2] == player and board[5] == player and board[8] == "-":
                      board[8] = comp
                  elif board[2] == player and board[8] == player and board[5] == "-":
                      board[5] = comp
                  elif board[8] == player and board[5] == player and board[2] == "-":
                      board[2] = comp
                  # Daigonal 1
                  elif board[0] == player and board[4] == player and board[8] == "-":
                      board[8] = comp
                  elif board[0] == player and board[8] == player and board[4] == "-":
                      board[4] = comp
                  elif board[8] == player and board[4] == player and board[0] == "-":
                      board[0] = comp
                  # Daigonal 2
                  elif board[2] == player and board[4] == player and board[6] == "-":
                      board[6] = comp
                  elif board[2] == player and board[6] == player and board[4] == "-":
                      board[4] = comp
                  elif board[6] == player and board[4] == player and board[2] == "-":
                      board[2] = comp
                  else:
                      if board[0] == player and board[4] == comp and board[7] == player and board[3] != player and board[
                          3] != comp:
                          board[3] = comp
                      elif board[0] == player and board[4] == comp and board[7] == player and board[3] == comp and board[
                          5] == player and board[2] != comp and board[2] != player:
                          board[2] = comp
                      elif board[0] == player and board[1] != comp and board[1] != player:
                          board[1] = comp
                      elif board[6] == "-":
                          board[6] = comp
                      elif board[8] == "-":
                          board[8] = comp
                      elif board[2] == "-":
                          board[2] = comp
                      elif board[0] == "-":
                          board[0] = comp
                      elif board[5] == "-":
                          board[5] = comp
                      elif board[7] == "-":
                          board[7] = comp
                      elif board[3] == "-":
                          board[3] = comp
                      elif board[1] == "-":
                          board[1] = comp

      # Conditions to ensure that Computer take its winning move first...


              def bot_win():
                  global player, comp
                  # Row 1
                  if board[0] == comp and board[1] == comp and board[2] == "-":
                      board[2] = comp
                  elif board[0] == comp and board[2] == comp and board[1] == "-":
                      board[1] = comp
                  elif board[2] == comp and board[1] == comp and board[0] == "-":
                      board[0] = comp
                  # Row 2
                  elif board[3] == comp and board[4] == comp and board[5] == "-":
                      board[5] = comp
                  elif board[3] == comp and board[5] == comp and board[4] == "-":
                      board[4] = comp
                  elif board[5] == comp and board[4] == comp and board[3] == "-":
                      board[3] = comp
                  # row 3
                  elif board[6] == comp and board[7] == comp and board[8] == "-":
                      board[8] = comp
                  elif board[6] == comp and board[8] == comp and board[7] == "-":
                      board[7] = comp
                  elif board[8] == comp and board[7] == comp and board[6] == "-":
                      board[6] = comp
                  # Column 1
                  elif board[0] == comp and board[3] == comp and board[6] == "-":
                      board[6] = comp
                  elif board[0] == comp and board[6] == comp and board[3] == "-":
                      board[3] = comp
                  elif board[6] == comp and board[3] == comp and board[0] == "-":
                      board[0] = comp
                  # Column 2
                  elif board[1] == comp and board[4] == comp and board[7] == "-":
                      board[7] = comp
                  elif board[1] == comp and board[7] == comp and board[4] == "-":
                      board[4] = comp
                  elif board[7] == comp and board[4] == comp and board[1] == "-":
                      board[1] = comp
                  # Column 3
                  elif board[2] == comp and board[5] == comp and board[8] == "-":
                      board[8] = comp
                  elif board[2] == comp and board[8] == comp and board[5] == "-":
                      board[5] = comp
                  elif board[8] == comp and board[5] == comp and board[2] == "-":
                      board[2] = comp
                  # Daigonal 1
                  elif board[0] == comp and board[4] == comp and board[8] == "-":
                      board[8] = comp
                  elif board[0] == comp and board[8] == comp and board[4] == "-":
                      board[4] = comp
                  elif board[8] == comp and board[4] == comp and board[0] == "-":
                      board[0] = comp
                  # Daigonal 2
                  elif board[2] == comp and board[4] == comp and board[6] == "-":
                      board[6] = comp
                  elif board[2] == comp and board[6] == comp and board[4] == "-":
                      board[4] = comp
                  elif board[6] == comp and board[4] == comp and board[2] == "-":
                      board[2] = comp

      # Winning Conditions..

              def check_win():
                  check_row()
                  check_column()
                  check_daigonal()
                  check_Tie()

             # Check Tie od a game

              def check_Tie():
                  global winner
                  global Game_continue
                  if "-" not in board:
                      winner = "nobody"

                      Game_continue = False

              # Check Winning conditions row wise

              def check_row():
                  global Game_continue
                  global winner
                  row1 = board[0] == board[1] == board[2] != "-"
                  row2 = board[3] == board[4] == board[5] != "-"
                  row3 = board[6] == board[7] == board[8] != "-"
                  if row1 or row2 or row3:
                      Game_continue = False
                  if row1:
                      winner = board[0]
                  if row2:
                      winner = board[3]
                  if row3:
                      winner = board[6]


              # Check Winning conditions Column wise

              def check_column():
                  global winner
                  global Game_continue
                  column1 = board[0] == board[3] == board[6] != "-"
                  column2 = board[1] == board[4] == board[7] != "-"
                  column3 = board[2] == board[5] == board[8] != "-"
                  if column1 or column2 or column3:
                      Game_continue = False
                  if column1:
                      winner = board[0]
                  if column2:
                      winner = board[1]
                  if column3:
                      winner = board[2]


              # Check Winning conditions Diagonal wise

              def check_daigonal():
                  global winner
                  global Game_continue
                  daigonal1 = board[0] == board[4] == board[8] != "-"
                  daigonal2 = board[2] == board[4] == board[6] != "-"

                  if daigonal1 or daigonal2:
                      Game_continue = False
                  if daigonal1:
                      winner = board[4]

                  if daigonal2:
                      winner = board[4]


              # It serve as a main funtions for single player mode

              def play_game():
                  global q
                  w = "y"
                  c = 1
                  global player, comp
                  while w == "y" or w == "Y":
                      if c >= 2:
                          q = int(find_mode())
                          print(q)
                          if q == 2:
                              break
                          elif q == 3:
                              break
                      c += 1

                      a = input('Enter your name :')
                      a = a.capitalize()
                      symbol = input(a + " Choose your character \"X\"  or  \"O\" ")

                      while symbol.upper() != "X" and symbol.upper() != "O":
                          print(a, " Wrong Symbol Please Input again:, Enter value either \"X\"  or  \"O\": ")
                          symbol = input("")
                      if symbol.upper() == "X":
                          player = "X"
                          comp = "O"

                      elif symbol.upper() == "O":
                          player = "O"
                          comp = "X"
                      import random
                      coin = ['Heads', 'Tails', 'head', 'tail', 'Head', 'Tail', 'heads', 'tails']
                      r = random.choice(coin)
                      toss = input(a + " Heads  or Tails: ")
                      while (toss != 'Heads' and toss != 'Tails' and toss != 'Head' and toss != 'Tail' and \
                             toss != 'heads' and toss != 'head' and toss != 'tails' and toss != 'tail'):
                          toss = input(a + " Please Select again Correct Option")

                      if r == toss:
                          print(a, " You Won the toss pick your first move")
                          Display_board()

                          while Game_continue:
                              input_Conditions()
                              bot_win()
                              check_win()
                              if Game_continue == False:
                                  break
                              bot_cond()
                              Display_board()
                              check_win()
                              if Game_continue == False:
                                  break
                      else:
                          print("Computer win the toss and will go first")
                          Display_board()
                          bot_win()
                          bot_cond()
                          Display_board()
                          while Game_continue:
                              input_Conditions()
                              bot_win()
                              check_win()
                              if Game_continue == False:
                                  break
                              bot_cond()
                              Display_board()
                              check_win()
                              if Game_continue == False:
                                  break

                      Display_board()
                      if winner == player:
                          print("                                   Congratulation", a, " You have won the game      ")
                          w = input(
                              "                           Enter Y or y to Run the game otherwise type anything else to finish:")
                      elif winner == comp:
                          print("                                                 Computer won the game                  ")
                          w = input(
                              "                           Enter Y or y to Run the game otherwise type anything else to finish:")
                      else:
                          print(
                              "                                                        Game Draw                           ")
                          w = input(
                              "                           Enter Y or y to Run the game otherwise type anything else to finish:")
                      recreate_board()


              print("                                                 Play Game                     ")
              play_game()  # calling play_game() function...

      # if user select a Multiplayer mode...


          if q == 2:
              import random
      # Asking again if he wants to play or exit
              Enter = input(
                  "         IF YOU WANT TO PLAY THE GAME PRESS Y, IF YOU WANT TO EXIT PRESS N:")  # start or Exit choice
              while Enter != 'Y' and Enter != 'N':
                  Enter = input("                           Wrong Input, Enter Again:")
              if Enter == "N":
                  exit()
              k = 0
              while Enter == "Y":
                  k += 1
                  if k >= 2:
                      q = int(find_mode())
                      if q == 1 or q == 3:
                          break
                  # main menu
                  print('                              Well Come to the Multiplayer TIC TAC TOE Game')
                  a = input('Enter Name of 1st Player: ')  # Player 1.
                  a = a.capitalize()
                  b = input('Enter Name of 2nd Player: ')  # Player 2.
                  b = b.capitalize()


                  # Toss


                  coin = ['Heads', 'Tails', 'tail', 'head', 'Tail', 'Head', 'tails', 'heads']
                  r = random.choice(coin)
                  toss = input(a + " Heads  or Tails: ")


                  while (toss != 'Heads' and toss != 'Tails'):
                      toss = input("Heads  or tails again 1st letter should be Capital: ")
                  if toss == r:
                      str(print(a, 'You Won the Toss.'))
                      tosswinner = a
                      tosslosser = b
                  else:
                      str(print(b, 'You Won the Toss'))
                      tosswinner = b
                      tosslosser = a


                  # Symbol


                  Symbol2 = input("Choose your Symbol X or O " + tosswinner + ":")
                  while Symbol2 != 'X' and Symbol2 != 'O':
                      Symbol2 = input("Choose your Symbol again X or O and must be capital " + tosswinner + ":")
                      if Symbol2 == "X":
                          Symbol1 = "O"
                      elif Symbol2 == "O":
                          Symbol1 = "X"


                  # defening_board

                  board = ['1', '2', '3', '4', '5', '6', '7', '8', '9']


                  def showboard(board):
                      print(board[0] + ' | ' + board[1] + ' | ' + board[2] + ' | ')
                      print('-----------')
                      print(board[3] + ' | ' + board[4] + ' | ' + board[5] + ' | ')
                      print('-----------')
                      print(board[6] + ' | ' + board[7] + ' | ' + board[8] + ' | ')


                  showboard(board)
                  print("                              position 1 is for the Player who Won the Toss")
                  print("                              position 2 is for the Player who Loss the Toss")

                  # Game_Start


                  man = Symbol2
                  position = 1
                  count = 1
                  while count <= 9:

                      position = str(
                          input('its your position ' + str(position) + ' Enter ' + man + ' at a position you want: '))
                      while position != '1' and position != '2' and position != '3' and position != '4' and position != '5' \
                              and position != '6' and position != '7' and position != '8' and position != '9':
                          position = str(input('its your position ' + str(position) + ' Enter ' + man +
                                               ' at a position you want Please Enter Correct Number: '))

                      position = int(position)
                      position = position - 1

                      if board[position] == 'X' or board[position] == 'O':
                          print(
                              '                                  Please Select another Position it is already occupied                   ')
                          continue
                      else:
                          board[position] = man
                      showboard(board)
                      count = count + 1

                      #Winning Conditions...


                      if board[0] == board[3] == board[6]:
                          if board[0] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[1] == board[4] == board[7]:
                          if board[1] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[2] == board[5] == board[8]:
                          if board[2] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[0] == board[1] == board[2]:
                          if board[0] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[3] == board[4] == board[5]:
                          if board[3] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[6] == board[7] == board[8]:
                          if board[6] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[0] == board[4] == board[8]:
                          if board[0] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      elif board[2] == board[4] == board[6]:
                          if board[2] == Symbol2:
                              print(tosswinner, 'Wins')
                          else:
                              print(tosslosser, 'Wins')
                          break

                      # Tie/Draw Condition...

                      elif count == 10:
                          print('Its Draw')
                          break
                      #Exchanging Symbol & Postions after every move

                      if position == 1:
                          position = 2
                          if man == 'X':
                              man = "O"
                          elif man == 'O':
                              man = "X"

                      else:
                          position = 1
                          if man == "X":
                              man = "O"
                          elif man == "O":
                              man = "X"

                  Enter = input(
                      "                  IF YOU WANT TO REPLAY THE GAME PRESS Y, IF YOU WANT TO EXIT PRESS N and anyother thing to exit:")

                  # If user select option 3
      if q == 3:
          print("                                                                  Thank You for visiting                 ")
          exit()    
