#Text Based RPG
#Menus etc
#Fight system that will be used for the whole game
#but help me in designing a load and save function
#and tell me how i can imrpove the code

import random

def main():
    input(" ")

def prefight():
    prefight1()

def prefight1():
    print ("Would you like to fight a Goblin? ")
    select1 = input ("-> ")
    if select1 == 'N' or select1 == 'n' or select1 == 'no' or select1 == 'No':
        print ("You are not fighting.")
        start2()
    elif select1 == 'Y' or select1 == 'y' or select1 == 'yes' or select1 == 'Yes':
        GoblinName = str("Goblin")
        GoblinAttack = 5
        GoblinHealth = 15
        GoblinMaxHealth = GoblinHealth
        GoblinGoldgain = 10
        PlayerAttack = 10
        PlayerHealth = 30
        PlayerMaxHealth = PlayerHealth
        PlayerGold = 0
        print ("You have entered a fight.")
        print (PlayerName, "vs. ", GoblinName)
        print (PlayerName,"'s Health:", PlayerHealth,"/",PlayerMaxHealth,"  ",GoblinName,"'s Health:", GoblinHealth,"/",GoblinMaxHealth)
        print (PlayerName,"'s Attack:", PlayerAttack,"  ",GoblinName,"'s Attack:", GoblinAttack)
        print ("Gold: ", PlayerGold)
        select3 = random.randint(1,2)
        selecta3 = random.randint(1,2)
        selectb3 = random.randint(1,2)
        while GoblinHealth > 0 and PlayerHealth > 0:
            if select3 == 1:
                if selecta3 == 1:
                    GoblinHealth = GoblinHealth - PlayerAttack
                    print (GoblinName,"'s Health: ", GoblinHealth,"/",GoblinMaxHealth)
                    print ("You dealt", PlayerAttack,"damage.")
                elif selecta3 == 2:
                    GoblinHealth = GoblinHealth - (PlayerAttack / 2)
                    print (GoblinName,"'s Health: ", GoblinHealth,"/",GoblinMaxHealth)
                    print ("You dealt", (PlayerAttack / 2),"damage.")
            elif select3 == 2:
                if selectb3 == 1:
                    PlayerHealth = PlayerHealth - GoblinAttack
                    print (PlayerName,"'s Health: ", PlayerHealth,"/",PlayerMaxHealth)
                    print ("The Goblin dealt", GoblinAttack,"damage.")
                elif selectb3 == 2:
                    PlayerHealth = PlayerHealth - (GoblinAttack / 2)
                    print (PlayerName,"'s Health: ", PlayerHealth,"/",PlayerMaxHealth)
                    print ("The Goblin dealt", GoblinAttack / 2,"damage.")
            GoblinHealth <= 0 or PlayerHealth <= 0
            if GoblinHealth <= 0:
                print ("You win!")
                PlayerGold = PlayerGold + GoblinGoldgain
                print ("Gold: ", PlayerGold)
                postfight()
            if PlayerHealth <= 0:
                print ("You lose!")
                postfight()

def postfight():
    print ("Would you like to go to Main Menu or the Start Menu? ")
    select2 = input ("-> ")
    if select2 == 'main' or select2 == 'Main':
        start2()
    elif select2 == 'start' or select2 == 'Start':
        start1()

def start2():
    print ("Menu")
    print ("1) Fight")
    print ("2) Store")
    print ("3) Save")
    select1 = input ("-> ")
    if select1 == '1':
    	prefight()
    elif select1 == '2':
    	store()
    else:
    	load()


def start1():
    print ("Welcome to Alderstone!")
    print ("1) Start ")
    print ("2) Exit ")
    print ("3) Load ")
    select = input ("-> ")
    if select == '1':
        start2()
    elif select == '2':
        quit1()
    else:
        load()

def quit1():
    exit

            
print ("What is your name? ")
PlayerName = input("-> ")
print ("Hello,",PlayerName)
start1()
