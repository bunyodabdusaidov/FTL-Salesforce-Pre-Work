# Pre-work - *Memory Game*

**Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: **BUNYOD ABDUSAIDOV**

Time spent: **~30** hours spent in total

Link to project: https://glitch.com/edit/#!/prework-bunyodabdusaidov | Live site: https://prework-bunyodabdusaidov.glitch.me

## Required Functionality

The following **required** functionality is complete:

* [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [x] "Start" button toggles between "Start" and "Stop" when clicked. 
* [x] Game buttons each light up and play a sound when clicked. 
* [x] Computer plays back sequence of clues including sound and visual cue for each button
* [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [x] User wins the game after guessing a complete pattern
* [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [x] Buttons use a pitch (frequency) other than the ones in the tutorial
* [x] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [x] Computer picks a different pattern each time the game is played
* [x] Player only loses after 3 mistakes (instead of on the first mistake)
* [x] Game button appearance change goes beyond color (e.g. add an image)
* [x] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [x] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [x] Game is actually gamified with levels. Difficulty increases each new level. Players can see their level
- [x] Players can see how many mistakes they made out of maximum possible mistakes in each sequence
- [x] Popup window shows up on each new level, and when player loses or wins. Players can choose to continue to next level, stop the game, or restart the game

## Video Walkthrough (GIF)

If you recorded multiple GIFs for all the implemented features, you can add them here:

1. Demo of basic requirements; images when buttons pressed; mistake and level counters; countdown timer; and popup window when player goes to next level. Images inspired by Bored Ape Yacht Club (NFT project)

![](http://g.recordit.co/VrpeTsqyCo.gif)

2. Demo of next button performance; mistake counter performance; level counter performance; random pattern performance.

![](http://g.recordit.co/09xuWigGu3.gif)

3. Demo of countdown timer performance; change of colors from green to orange to red when 20 seconds, 10 seconds, and 5 seconds left (respectively); popup window performance when player loses the game; restart button performance

![](http://g.recordit.co/D6c7rghCjS.gif)

4. Demo of clue hold time performance; random pattern performance on each new level; popup window performance when player wins the game. (I had to set `MAX_LEVEL = 2` for demonstration purposes)

![](http://g.recordit.co/wwbmaXgM2J.gif)

## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 

* I mainly used knowledge gained through online courses and especially from CS50x course provided by Harvard university. I learned HTML, CSS through Udemy online courses and JS in CS50x courses & challenges. 

* I used https://w3schools.com, https://geeksforgeeks.com, https://stackoverflow.com, https://developer.mozilla.org as a general guide/resource in implementing my solutions for optional and additional features. I used https://css-tricks.com/how-to-create-an-animated-countdown-timer-with-html-css-and-javascript/ for implementing countdown timer in optional feature #6.

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 

* I struggled quite a bit in doing the **optional feature #5**, in particular, making the buttons change to image when active, onmousedown, and onmouseup. I came up with different solutions. I tried to insert `<img></img>` tag into and/or before `<button></button>` tag and make images hidden with `<img class="hidden">`. Changed the style of images in `style.css` to be aligned exactly the same as buttons and with the same size as buttons. In `script.js`, I implemented a function called `showImage(btn)` which will remove and add the `class="hidden"` whenever the function is called and called that function in `playSingleClue(btn)`, `onmousedown=""`, and `onmouseup=""`. And, it didn't work. I tried make buttons to be hidden and images to be shown when the function is called, onmousedown, and onmouseup. It didn't work. The problem was in how the image and button not being on top of each other. My goal was to make images appear on top of the buttons. According to HTML rules, I believe, since each element has it own area, my first and second solutions didn't work. But, after some research, I found a way to make it work. I inserted the image source into button's background when `showImage(btn)` is called: `button.style.background = imageSource;`. But, in order to make image dissappear after button is active and onmouseup, I inserted empty image source into button's background in `hideImage(btn)` function: `button.style.background = "";`. In `index.html`, called the functions: `onmousedown="showImage(btn)" onmouseup="hideImage(btn)"`. In `playSinceClue(btn)`, called `showImage(btn)` to show images when button is active, and called `setTimeout(hideImage,clueHoldTime,btn);` with `setTimout` function with the same `clueHoldTime` so that the image will dissappear when the clue time is out.

* Implementing the **optional feature #6** was an interesting challenge as well. Although I used internet resource, I learned about `<path></path>` tag and `stroke-dasharray`, specifically, how we can draw different shapes using `<path></path>` tag and its properties. I had to separate `HTML` and `JS` script to achieve clean code and consistency in styling. 

* In **additional features (score and mistake counter)**, I had an issue with showing the correct number of mistakes and/or score of player when the player wins and loses the game. The solution was in `alert` function in `script.js`, it was executing earlier than `displayMistakes()` and `displayScore()` functions show the last mistake and score. After reading about order of scripts in `Javascript`, I decided to use `setTimout()` with `winGame()` and/or `loseGame()` functions so that these functions execute later, with a little delay, after `displayMistakes()` and `displayScore()` finish running. 

* Implementing the popup window was not a big issue since I gained enough experience and knowledge during the project and had an idea of how to implement it. It took quite a bit of time, though.

3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 

* I am now more interested in learning `Javascript` frameworks like `ReactJs` or `NodeJs` because while doing the pre-work assignment, I found many easy solutions in `ReactJs` and/or `NodeJs` including other powerful frameworks. Since I am interested more in backend development, facing with `Javascript`, I realized that how powerful language `Javascript` is and why it is so popular. After learning more about `Javascript`, I came up with many different ideas to finish the `Problem Set 9` in CS50x course. 

* I really want to learn about optimal solution practices for fast, dynamic, and secure application development, because while implementing the optional and additional features, I came up with different solutions, such as doing most work in `script.js` or `index.html`. Also, I wonder whether we can have different `script` files, like modules in `Python`, so that we can separate our implementations. For example, I would separate the script with basic implementations into one module, functions for showing and hiding the images into another module, and the countdown timer into another. This way it would be easier to maintain the application in case I should add additional features, and we could use these modules in other applications.

4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 

* If I had more time, I would refactor the countdown timer so that it starts right after the clue sequence. Currently, it starts at the same as the clue sequence. Due to time contraints, I could not fix it, but I know what exactly I would do. I am not sure it is right thing to do though. 

* I would make the sounds be in in the order of "do, re, mi, fa, so, la, si" on each clue sequence. For this, I would have to create a loop and add specific conditions that would change sounds sequence according to the pattern.

* I would create a leaderboard which shows the players and their scores worldwide. I would create an API with Flask and SQLite, connect to server, and so on. I haven't worked with servers yet so that I could implement a feature which allows any online player to be able to play the game and show up on the leaderboard. I would love to learn about it, though, during the process. 

* I would definitely look at how I can make my code DRY because I feel like I repeated some implementations whereas I could make them to be used generically. I would improve styles and add some animations like in real games.

* I would also make so that players can participate in a contest and win very cheap NFTs or small of portions of cryptocurrencies; just to make the game more interesting. 

## Interview Recording URL Link

[My 5-minute Interview Recording](https://www.loom.com/share/055e0d8cfb52445eb6266acd75247a9c)


https://user-images.githubusercontent.com/65746829/164872782-10b715a0-73c7-42b0-aec6-f1c9a2e7ce6b.mp4


## License

    Copyright [BUNYOD ABDUSAIDOV]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
