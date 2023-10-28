# CPSC 8710 - Foundations of Software Engineering - Memory Game
  
## Index – Table of Contents 

* [About](#About)
* [Game Layout](#Game-Layout) 
* [Game Requirements](#Game-Requirements)
* [Logic](#Game-Logic)
* [User Stories](#user-stories)
* [Features](#features) 
* [Technologies Used](#technologies-used) 
* [Testing](#testing) 
* [Setup Instructions for Local](#Setup-Instructions-for-Local) 
* [Acknowledgements](#credits)

***

  

## About   

As part of our Foundations of Software Engineering coursework, we have created a web-based memory game called "Christmas Matches" with a Christmas theme. The primary goal of this game is to evaluate a player's memory skills. It involves a deck of cards, each featuring a randomly assigned image. Players need to click on a card to reveal the image, memorize its location, and then match cards with identical images until all pairs have been successfully matched.

<p align="center">
  ![image](https://github.com/HiralThadeshwar31/CPSC-8710-Memory-game/assets/55878934/f1a3b0a7-fce7-4e68-b319-a916e5c7c18d)
</p>

 ## Challenge
 
 The challenge is to complete the matching of all the cards in the shortest amount of time while making the fewest possible selections.

*** 

## Instructions

* Select your preferred difficulty level (Easy, Medium, Hard) to initiate the game.

* Click on the blocks to unveil the images hidden behind them. Continue this process with the remaining blocks, aiming to discover matching pairs.

* Keep uncovering cards and put your memory to the test, remembering each card you reveal.

* Efficiently match the cards with as few moves as possible and complete the game in the shortest time.

* If needed, you can reset the game by using the "Reset" button.

* Monitor the game's progress with the "Timer" displayed at the top.

* To return to the home page, simply click the home button.

 ***

## Game Layout

The index page is equipped with a modal providing instructions on how to play the game. It also features a "Start Game" button, which, when clicked, directs users to the game page. Users are given the choice to select their preferred difficulty level and begin playing from there. By default, clicking the "Start Game" button will lead users to the Easy level.

The game page itself is inclusive of a header and a score panel that monitors various performance metrics, including time, moves, and the user's current star rating, which is determined by their performance. Additionally, a reset button is available to allow users to restart the game.

The game board is constructed using a card deck that adapts according to the selected difficulty level. These cards are generated dynamically through JavaScript. Each card is designed with a front and back face. When a user hovers over a card, its background brightens, and upon clicking, the card flips to reveal an image. It is crucial for players to memorize these images in order to enhance their performance.

Upon successfully completing the game, a "Win-Game" Modal emerges at the center of the screen, delivering feedback on the user's grade, star rating, and the time taken to finish the game.

To ensure responsiveness, the card deck was created using CSS grid.

For the game's text, the fonts Lobster and Georgia were chosen due to their high readability and game-friendly appearance. These fonts also convey a slightly comical feel, which aligns with the game's overall goal.
***

## Game Requirements

* On load or restart, the cards must be shuffled and a random array of images is to be generated.

* The game needs to be able to handle both matched and unmatched cards.

* Cards need to make a sound when flipped, a success sound when they match, an error sound when unmatched and a victory sound when game is completed.

* Cards must not be clickable when they are already open.

* Game should be able to display the number of moves or clicks a user has made.

* Game must display a timer that starts when the first click is made, and ends when the last pair of cards has been matched.

* Game should be able to display a star rating that indicates a user's performance, based on the number of moves made.

* The more moves a user makes, the user rating decreases. 

* A reset button that shuffles the images array, resets timer and star rating, and reassigns those reshuffled images to the cards.

* A win game modal displayed when the game is completed to congratulate the user.

* Win Game modal is updated with user's game stats and displayed at the end of the game to provide feedback. 

* Win game modal needs to have the option to ask the user to play again.

***
 
## Game Logic 

* An array is utilized to store image paths, which are then assigned to the cards and displayed on their backfaces.

* Two arrays are used: one to store opened cards and another to store matched cards.

* There's a function responsible for shuffling the images array when the game is loaded.

* Another function initiates the game, which includes invoking the shuffle function, assigning random images to each card, and appending these cards to the deck.

* A timer function is implemented and called in the card event listener, updating the innerHTML every 1-second interval from the moment a card is clicked.

* A stopTime function is in place to clear the time function interval.

* A reset function is available to reset all global variables and the content of HTML elements, including the timer, stars, moves, and their innerHTML, while also emptying all arrays.

* A movesCounter function is utilized to keep track of the number of moves made during the game.

* A function is employed to update the star rating based on the number of moves made by the player to complete the game. The star rating decreases as the player makes more moves.

* Another function is used to compare two cards in the openedCards array when its length is 2, determining whether they form a match or not. If they match, they are added to the matched cards array; otherwise, they are removed from the openedCards array.

* There is a function responsible for retrieving player statistics and providing feedback based on these statistics.

* A function is employed to display the win-game modal.

* The Win-game function displays the win-game modal when the game is completed, calls the stats function, and stops the timer function.

* A function is in place to handle clicked cards, apply a flip animation, play audio, reveal the backface, and add card content to the openedCards array.

***

## User Stories

As a user, my preferences include:

* Enjoying a visually captivating and user-friendly game that offers a fun and challenging experience.
* Expecting to be rated based on my performance, motivating me to improve.
* Having the ability to click on any card to reveal it as the first card and then selecting another card, which should also turn to reveal its image.
* Desiring the option to restart the game whenever I choose.
* Experiencing a responsive game that I can enjoy on both mobile and desktop devices.
* Relishing a Halloween-themed game to align with its title and create a festive atmosphere.
* Receiving confirmation and performance feedback upon successfully completing the game, giving me a sense of accomplishment.
* Wanting the flexibility to play at different difficulty levels, allowing me to tailor the game to my skill level.
* Navigating through a main menu that lets me choose to start the game or access instructions.

***

## Features
### Existing features
#### Home
* An instructions modal that is easy to understand and navigate, guiding the user effectively.
* A clear and compelling call to action that motivates the user to take the desired step, such as initiating the game on the home page.

#### Game page
* Game cards that are interactive, clickable, and flip over when clicked.
* The game's logic dictates that when a match is found, the cards animate and stay visible.
* A moves counter keeps track of the number of moves, updating after each pair of cards is turned.
* Upon completing the game, a game over modal appears, featuring a congratulatory header.
* A compelling call to action prompts the user to restart the game.
* Evaluation and feedback messages are presented based on the user's performance, encouraging them to try again and beat their best score.
* The option to reset the score and restart the game is available at any stage.

#### Features that can be implemented
* A high all-time leaderboard displaying the overall statistics of all users.
* Auditory cues designed to aid in memorization during gameplay.
* The addition of a timed mode, introducing a timer to enhance the game's challenge, requiring players to finish the game before the timer expires.

***

## Technologies Used
* HTML
* CSS
* Javascript
* Google Fonts
* Font Awesome Library
* Chrome Developer Tools
* Markup Validation Service
* CSS Validation Service
* JSHint for testing JS code
* Am I responsive
* Gitpod.io - for writing the code. Using the command line for committing and pushing to GitHub 
* GitHub - Used to host repository  
* GIT - for version control of the project. 

***

## Testing

### HTML

Both the index and the home pages passed the HTML W3C Markup Validation Service with no errors.

### CSS

Both the index and home pages passed the W3C CSS validation Service with no errors shown.

### Responsiveness

As a backup to using Chrome developer tools to check for responsiveness across multiple devices, I have also used http://ami.responsivedesign.is and was very pleased with the outcome, and the game layout across various screen sizes.

***

## Setup Instructions for Local:

* To obtain the repository, execute "Git clone git@github.com:HiralThadeshwar31/CPSC-8710-Memory-game.git" in your terminal.
* Navigate to the game's directory by changing your current directory.
* Launch the game locally by opening the index.html file in a web browser.

***

## Credits

* [W3C schools](https://www.w3schools.com/)
* [Mozilla Developer Networks](https://developer.mozilla.org/en-US/)
* [Flaticon.com](https://www.flaticon.com/) for the all images used in the project
* Kris DeBruine Media - [How to shuffle an array](https://www.youtube.com/watch?v=79AWYPyPEdU)
* Adam Khoury - [Visualising the Fisher-Yates shuffle method](https://www.youtube.com/watch?v=tLxBwSL3lPQ&t=423s)
* FreeCodeCamp.org for tutorials regarding breaking down Memory game logic
* [Sandra Israel's Memory game process for inspiration](https://scotch.io/tutorials/how-to-build-a-memory-matching-game-in-javascript#toc-what-is-the-memory-game) 
* Flip Cards based on [W3C flip card tutorial](https://www.w3schools.com/howto/howto_css_flip_card.asp)
* [SVG Backgrounds](https://www.svgbackgrounds.com/) for free customisable SVG Backgrounds.
* [CSS gradient generator](https://cssgradient.io/)
