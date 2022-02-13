# Coin-Flip-Experiment
Write a code that counts how many streaks of 6 heads and 6 tails occur in a row in a sample size of 10,000
import random

heads = 0
tails = 0
results = [ ]
stringResults = ' '
numberOfStreaks = 0

# Executes the "coin flip"

for coinFlip in range(10000):
    coinFlip = random.randint(0,1)
    results.append(str(coinFlip))
    if coinFlip == 0:
        heads += 1
    elif coinFlip == 1:
        tails += 1

#  Count the number of times a streak of heads or tails is present in my results
stringResults = stringResults.join(results) # this turns my results of the coinflips into a string
count_streak0 = stringResults.count('0 ' * 6)
count_streak1 = stringResults.count('1 ' * 6)
numberOfStreaks = count_streak0 + count_streak1

print('Heads = ' + str(heads))
print('Tails = ' + str(tails))
print('Number of streaks = ' + str(numberOfStreaks))
print('Chance of streak: %s%%' % (numberOfStreaks / 100))
