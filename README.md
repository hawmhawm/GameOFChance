# GameOFChance
GAME OF Chance with a Balance and Other Cool Stuff.



import random

value = input('Whats Your Name?')
if value.startswith('s') or value.startswith('S'):
    print('Szia', value, '!')
else:
    print('Hello', value, '!')

Money = 300
isQuit = ""
while isQuit != 'y':

    Bet = 0
    print('Your cash:', Money, '$')
    while Bet == 0:
        Betstr = input("Place Your Bet! OR Press q for Quit!")
        if Betstr.isnumeric():
            Bet = int(Betstr)
            if Bet > Money:
                Bet = 0
                print("You Have no Money!")
            else:
                FirstDice = random.randint(1, 30)

                print(FirstDice)

                playerWinList = [(2), (3), (5), (7), (11), (13), (17), (19), (23), (29)]
                playerWinList2 = [(2), (4), (6), (8), (10), (12), (14), (18), (24), (28)]
                playerWinList3 = [(10), (20), (30)]
                computerWinList = [(1), (2), (3), (1), (2)]
                if playerWinList.__contains__((FirstDice)):
                    print("Contains")
                    Money = Money+Bet*5
                if playerWinList2.__contains__((FirstDice)):
                    print("Contains")
                    Money = Money+Bet*2
                if playerWinList3.__contains__((FirstDice)):
                    print("Contains")
                    Money = Money+Bet*3                  
                elif computerWinList.__contains__((FirstDice)):
                    print("You lose")
                    Money = Money - Bet
                else:
                    print("draw")
        elif Betstr.__contains__('q'):
            isQuit = input('Do you want to quit?')
            print(isQuit)
            break

    

