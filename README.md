# Quick Yahtzee
### https://quick-yahtzee.herokuapp.com

**Purpose:** This code is essentially a shortened version of "Yahtzee", a traditional game of chance that involves dice. It is designed for two users to play the game on a single browser.

**Languages:** HTML, CSS (with SASS), Javascript (with jQuery)

**Mobile-friendly?:** Yes

"Quick Yahtzee" is the first, independent work that I ever made using Javascript and jQuery. It was truly eye-opening for me as I learned the amazing, interactive capabilities of a modern website's basic tools. This also abruptly taught me many of the common mistakes that a beginner developer makes, as well as how often unpredictable human mistakes cause major bugs. Finally, this game also forced me to thoroughly understand every interaction within its code. 

***SCREEN LAYOUT***
- Laptop/Desktop: 
On the top of the screen are three buttons: RULES, HOW TO PLAY, and RESET SCORE. The RESET SCORE button simply refreshes this page which, in the process removes the player names and scores. A box appear after clicking RESET SCORE to confirm that the play does, in fact, want to reset the game.</br>
In the box to the right of the screen, users can see their name and scoreboards. The player whose turn it is has their name highlighted in orange. Any "category" highlighted in red has already been used and cannot be used again.</br> 
The green box in the center of the screen holds the dice. The dice are blank at the beginning of every turn until their first roll. Any selected dice will be shaded with grey. *(NOTE: due to a JS design, it may take one OR two clicks to select a die)* The player can select all or none of the dice. Beneath the dice are three buttons (ROLL, ENTER POINTS, and NEXT TURN) that the current player uses to a) roll their dice, b) accept their selected dice as their score, and c) end their turn in order to "hand the dice" over to the other player.</br>
In the box on the left of the screen, the eight ovals on top are buttons are where a player chooses which "category" or criteria for gaining points this turn (for more details, see "HOW TO PLAY"). The selected category will be shaded with grey. The two, larger ovals at the bottom of this box show you which turn you are on (max. 8) and how many times you have rolled on this turn (max. 3).

- Mobile: 
The mobile design is similar to the laptop design with two distinct differences.</br>
First, the "category" box (previously on the left) and "score" box (on the right) are now side-by-side, both of which are now beneath the "dice" box.</br>
Second, the three buttons (RULES, HOW TO PLAY, and RESET SCORE) along the top of the laptop design are now replaced with one button: MENU. Clicking on this button makes the three previous buttons slide down and into view.

***HOW TO PLAY***

As soon as the browser recieves the server's response, two prompts take place. This is where each user can enter their desired name. If a player leaves their prompt blank, then their default name will be "Player 1" or "Player 2". An alert then follows with a brief description of how to start the game, after which the first player can begin.</br>
The player should first click the "ROLL" button. This will fill each of the (previously blank) "dice" with random number from 1 to 6. The player can then select any of the dice by clicking on them until they are shaded black. The player can roll their dice a maximum of three times, and shaded dice will not change during a roll. When the player decides to add their turn's score, they must select a category and click "ENTER POINTS". If a) their selected dice meet the criteria of their chosen category and b) that category hasn't been used before, then the score will be added to that player's total score. Finally, the player then clicks "NEXT TURN", which moves onto the next player's turn. When both players have completed a turn, then they have just finished a "round". The game ends when they complete their 8th round, and the winner is the player with the highest total score. For the detailed rules, click on the game's "RULES" button.

***THE CODE***

Of course, it isn't worth explaining ALL of *Quick Yahtzee*'s code. However, below is a flow diagram depicting the series of functions,variables, etc. that is carried out when the player clicks the "Enter Points" button. This seemingly simple task became much more complex in order to prevent errors that would occur if a player clicks on the wrong buttons or if they click the correct buttons in the wrong order. For a description of the diagram:

1) The player click on the #pointsButton
2) The blockResubmit function prevents the player from entering points if it already did
3) The submitValues function enters all of the values of the dice that the player selected
4) The confirmEmpty function makes sure that the player hasn't already used the category (like "Yahtzee" or "Threes") that he used already
5) The checkValues function confirms that each selected dice meets the criteria of the chose category. It tallies the number of dice that pass inspection
6) If the number of accepted dice meets the number of dice that the player selected, then the points are added to the player's score.
7) All of the variables are now reset for the next player

<img src="views/images/enter_click.png">
