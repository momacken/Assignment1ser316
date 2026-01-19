BRANCH DESCRIPTIONS:
	MAIN branch:
		Contains the initial number guessing game with tests. Has the basic logic for the game, engine selects a random number then players guess the 	number. Program tells the player if the guess was "too high" or "too low". If player guesses correct number it displays correct along with the number 	of attempts.

	Feature1 branch:
		Adds a version header which documents the quit feature. Adds the ability to quit a match by typing in a negative number. Adds the ability to 	play again at end of match by pressing y for yes or n for no. Updated user feed back to be more specific, now it says "Too high! Try a lower number." 	and "Too low! Try a higher number.".

	Feature2 branch:
		Adds a losing condition to main. MAX_ATTEMPTS variable initialized to 10. If the player guesses more than 10 times the program outputs "Game 	Over, You've used all 10 attempts. The number was " with the target appended.

	Dev branch:
		Initially adds a "Good luck!" message after the welcome. This is the development branch where new features are added and tested before being 	committed onto the main branch.

	Feature3 branch:
		Adds a hint feature to the game. Hints are decided by the amount of attempts and the difference between the target and the guess. If the 	attempts are greater or equal to 3 and the difference is less than or equal to ten it prints " HINT: You're very close!". If the attempts are greater 	than or equal to 5 and the difference is less than or equal to 20 it prints " HINT: Getting warmer!". This branch also includes testing for the hint 	feature.

	Hotfix branch:
		Fixes the bug in the randomInt() function. Adds a + 1 so that the range is inclusive from the chosen min and max values.

LEARNING SUMMARY:
	Differences between merge, rebase, squash, and cherry-pick:

		Merge: Merge takes two branches and combines the changes from each using a merge commit. Conflicts need to be handled by the programmer. The 		two branches histories are preserved and you can see this on the graph for the git. This was used to merge feature2 with the dev branch.

 		*   86cd3a6 (HEAD -> dev) Merge branch 'main' into dev
		|\
		| * eba3870 (main) Gradlew windows fix
		| * 6ad2309 Fix randomInt to properly include max value in range
		example from the graph of a merge from main onto dev.

		Rebase: Rebasing moves the branch commits to the head of the targeted branch, in this case it was rebasing feature2 onto dev. This keeps the 		commit history linear. After a merge the rebase will appear to be a flat line of commits on a branch.

		* 718cb6c Implement max attempts logic and game over condition
		* 1806afc Add maxAttempts constant and game over state
		*   ddd53c5 Resolve conflict between message on dev and version header
		|\
		|
		example of merge after a rebase.

		Squash: Squash takes a commit and merges it with a commit on the same branch. This was used on feature three because it had multiple messy 		commits where the messages didn't add any clarity. Squashing the commits of feature3 allowed us to create one clean commit with the 			description "Add hint system to show proximity after 3 attempts".

		Cherry-pick: Cherry-pick lets you take a commit from a branch and apply it to a different branch. This was used to apply the hotfix commit 		from the hotfix branch onto the main branch.

	What I observed in the git history for feature1 vs feature2 vs feature3:
		feature1: Had the least amount of commits and merging it with dev was a lot easier than feature 2.
		feature2: Had Less commits but the merges were larger and added functionality which conflicted with the feature 1 branch.
		feature3: I observed that the commit history for this branch was composed of smaller commits but many of them which cluttered the history.  

	When I would use these git operations In real projects:
		Merge: I would use this if I needed to preserve the history of the separate branches. An example would be merging a feature branch onto a dev 		branch because this would allow others to see the commits made to the feature branch and how it connects to the dev branch.

		Rebase: I would use this when developing on a feature branch that needs to be updated with new code from the dev branch. This would keep the 		code of the feature and dev branch linear after a merge. 
	
		Squash: I would use this in a situation where I have multiple commits that would look cleaner and make more sense as a single commit. In the 		case of the guessing game this was when multiple small commits were made to the hint system. Squashing allowed me to clean up the commits of 		the feature3 branch before merging it into the dev branch.
	
		Cherry-pick: I would use this if I needed to apply a singular change from a different branch to the project. If there was a hotfix earlier on 		I could cherry-pick the commits hash and apply it to the main branch. I could also see this being useful if there is a couple of useful 		commits in a branch but it doesn't make sense to merge the entire branch.