MAIN branch:
	Contains the initial number guessing game with tests. Has the basic logic for the game, engine selects a random number then players guess the number. Program tells the player if the guess was "too high" or "too low". If player guesses correct number it displays correct along with the number of attempts.

Feature1 branch:
	Adds a version header which documents the quit feature. Adds the ability to quit a match by typing in a negative number. Adds the ability to play again at end of match by pressing y for yes or n for no. Updated user feed back to be more specific, now it says "Too high! Try a lower number." and "Too low! Try a higher number.".

Feature2 branch:
	Adds a losing condition to main. MAX_ATTEMPTS variable initialized to 10. If the the player guesses more than 10 times the program outputs "Game Over, You've used all 10 attempts. The number was " with the target appended.

Dev branch:
	Initially adds a "Good luck!" message after the welcome. This is the development branch where new features are added and tested before being commited onto the main branch.

Feature3 branch:
	Adds a hint feature to the game. Hints are decided by the amount of attempts and the difference between the target and the guess. If the attempts are greater or equal to 3 and the difference is less than or equal to ten it prints " HINT: You're very close!". If the attempts are greater than or equal to 5 and the difference is less than or equal to 20 it prints " HINT: Getting warmer!". This branch also includes testing for the hint feature.

HotFix branch:
	Fixes the bug in the randomInt() function. Adds a + 1 so that the range is inclusive from the chosen min and max values.