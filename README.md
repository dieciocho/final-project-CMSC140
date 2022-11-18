# final-project-CMSC140
This is a rock paper scissors game which players can choose either rock or paper or scissors then compete with automatic computer to see who wins, same rule as traditional rock paper scissors

I had some support through stack overflow research and prof. Ackles



import random as rand
from random import randint
import pandas as pd

list = ["Rock", "Paper", "Scissors"]
bot = list[randint(0,2)]
player = False
counter = 0 
leaderboard ={}

while player == False:
    player = input("Pick your weapon - Rock, Paper or Scissors:")
    if player == bot:
        print("Tie!")
        counter +=1
    elif player == "Rock":
        if bot == "Paper":
            print("You lose", bot, "beats", player)
            counter +=1
        else:
            print("You win", player, "beats", bot)
            counter +=1
            break
    elif player == "Paper":
        if bot == "Scissors":
            print("You lose", bot, "beats", player)
            counter +=1
        else:
            print("You win", player, "beats", bot)
            counter +=1
            
            break
    elif player == "Scissors":
        if bot == "Rock":
            print("You lose...", bot, "beats", player)
            counter +=1
        else:
            print("You win", player, "beats", bot)
            counter +=1
            
            break
    else:
        print("That's not a valid play. Check your spelling!")
    
    player = False
    


highscores = pd.read_csv("leaderboard.txt")
counter = {"Name": "Playername",
        "HighScore": 2}
highscores = highscores.append(counter, ignore_index=True)
highscores = highscores.sort_values(by=["HighScore"])
highscores.to_csv("leaderboard.txt", index=False)
