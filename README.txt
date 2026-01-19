MAIN branch:
	Contains the initial number guessing game with tests. Has the basic logic for the game, engine selects a random number then players guess the number. Program tells the player if the guess was "too high" or "too low". If player guesses correct number it displays correct along with the number of attempts.

Feature1 branch:
	Adds a version header which documents the quit feature. Adds the ability to quit a match by typing in a negative number. Adds the ability to play again at end of match by pressing y for yes or n for no. Updated user feed back to be more specific, now it says "Too high! Try a lower number." and "Too low! Try a higher number.".

Feature2 branch:
	Adds a losing condition to main. MAX_ATTEMPTS variable initialized to 10. If the player guesses more than 10 times the program outputs "Game Over, You've used all 10 attempts. The number was " with the target appended.

Dev branch:
	Initially adds a "Good luck!" message after the welcome. This is the development branch where new features are added and tested before being committed onto the main branch.

Feature3 branch:
	Adds a hint feature to the game. Hints are decided by the amount of attempts and the difference between the target and the guess. If the attempts are greater or equal to 3 and the difference is less than or equal to ten it prints " HINT: You're very close!". If the attempts are greater than or equal to 5 and the difference is less than or equal to 20 it prints " HINT: Getting warmer!". This branch also includes testing for the hint feature.

Hotfix branch:
	Fixes the bug in the randomInt() function. Adds a + 1 so that the range is inclusive from the chosen min and max values.

LEARNING SUMMARY:
Differences between merge, rebase, squash, and cherry-pick:

	Merge: Merge takes two branches and combines the changes from each using a merge commit. Conflicts need to be handled by the programmer. The two branches histories are preserved and you can see this on the graph for the git. This was used to merge feature2 with the dev branch.

 		*   86cd3a6 (HEAD -> dev) Merge branch 'main' into dev
		|\
		| * eba3870 (main) Gradlew windows fix
		| * 6ad2309 Fix randomInt to properly include max value in range
	example from the graph of a merge from main onto dev.

	Rebase: Rebasing moves the branch commits to the head of the targeted branch, in this case it was rebasing feature2 onto dev. This keeps the commit 	history linear. After a merge the rebase will appear to be a flat line of commits on a branch.

		* 718cb6c Implement max attempts logic and game over condition
		* 1806afc Add maxAttempts constant and game over state
		*   ddd53c5 Resolve conflict between message on dev and version header
		|\
		|
	example of merge after a rebase.

	Squash: Squash takes a commit and merges it with a commit on the same branch. This was used on feature three because it had multiple messy commits 	where the messages didn't add any clarity. Squashing the commits of feature3 allowed us to create one clean commit with the description "Add hint 	system to show proximity after 3 attempts".

	Cherry-pick: Cherry-pick lets you take a commit from a branch and apply it to a different branch. This was used to apply the hotfix commit from the 	hotfix branch onto the main branch.