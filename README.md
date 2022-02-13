# Coin-Flip-Experiment, one side face-up

import random

face_up = 0
face_down = 0
results = [ ]
stringResults = ' '
numberOfStreaks = 0

# This code executes the "coin flip"

for coinFlip in range(10000 ):
    coinFlip = random.randint(1,100)
    if coinFlip < 52: # result would be a number between 1 and 51 and will be considered face up
        results.append('U')
        face_up += 1
    else: # result would be face down
        results.append('D')
        face_down += 1

#  Count the number of times a streak is present in my results
stringResults = stringResults.join(results) # this turns my results of the coinflips into a string
count_streakU = stringResults.count('U ' * 6)
count_streakD = stringResults.count('D ' * 6)
numberOfStreaks = count_streakU + count_streakD


print('Face up = ' + str(face_up))
print('Face down = ' + str(face_down))
print('Number of streaks = ' + str(numberOfStreaks))
print('Chance of streak: %s%%' % (numberOfStreaks / 100))
