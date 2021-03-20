# Pre-work - *Memory Game*

**Nhi Not Simon** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: Nhi Nguyen

Time spent: 4 hours spent in total (including README)

Link to project: [https://glitch.com/edit/#!/satisfying-gelatinous-louse?path=README.md%3A9%3A20](https://glitch.com/edit/#!/satisfying-gelatinous-louse?path=README.md%3A9%3A20)

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
*(more specifically, the frequeny was changed to increasing order as another clue to help the player remember the sequence)*
* [ ] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [ ] Computer picks a different pattern each time the game is played
* [ ] Player only loses after 3 mistakes (instead of on the first mistake)
* [ ] Game button appearance change goes beyond color (e.g. add an image)
* [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [ ] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [x] **Regular vs Advanced Option**   
Instead of just forcing the speed of the game to increase, 
I gave the user the option to choose which version of the game they wanted to play by adding an additional start button. 
The regular Start button will run the default game but the Start (Adv) button will speed up the playClueSequence function.
In addition to changing the clueHoldTime variable as suggested, I also changed the cluePauseTime in order to make the sequence more smooth.
Once the game ends, the variables are then set back to their default values in the stopGame() method since they are no longer const.

## Video Walkthrough

Here's a walkthrough of implemented user stories:
![](your-link-here)
[Video demonstrating all app functionalities INCLUDING SOUND (Game Over message does not display in recording because I was only recording the current tab, not the full window. However, messages can bee seen in the GIFS)](https://www.loom.com/share/c9b1ef6832e04c869208db142ffe8983)
* Lose, in default mode   
![deafultMide](https://media1.giphy.com/media/l2EuPBp14KAciKFpBw/giphy.gif)

* Win, in Advanced mode (additional speed feature)   
![advMode](https://media3.giphy.com/media/3ZwJ41cHxjFxWo4tbQ/giphy.gif)


## Reflection Questions
1. **If you used any outside resources to help complete your submission (websites, books, people, etc) list them here.**    
* [23school.com for CSS font styling](https://www.w3schools.com/css/css_font_style.asp)   
* [colorhunt.co for picking color combination](https://colorhunt.co/)

2. **What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words)**
The most challenging aspect as getting the speed to increment (i.e. the hold time to decrement) properly. 
I wrote the pseudocode first to ensure that the logic made sense and then changed it into actual code when I pasted it into the index.hmtl file. 
Although the program ran, I didn't see any changes in the speed. 
I tried debugging the code with console.log() and found that I had forgotten to change the variable from "const" to "var," 
which prevented the change from occurring. The other aspect that was initially difficult was figuring out how much to decrease the hold time by. 
Eventually, through an iterative process of repeatedly testing different intervals, I found that reducing the hold time by 150 ms 
(down until the 200 ms limit to avoid sound playback confusion) was a good and steady amount. 
However, something still felt off. The increase in speed still wasn’t natural. I thought perhaps I still needed to tinker with the 
decreaseInHold variable but as I looked back at the playClueSequence() function, I realized that the cluePauseTime was what was causing the awkward 
wait. Because the pause-time wasn’t decreasing along with the decreasing hold-time, the overall sequence’s increase in speed felt unnatural. 
To fix this, I applied a similar process to the cluePauseTime variable as I did to the clueHoldTime variable and that seemed to resolve the issue. 

3. **What questions about web development do you have after completing your submission? (recommended 100 - 300 words)** 
* I would like to know how to save the user's input and information and have it still be retrievable after the user has exited the page and come back. I understand how to take in user input but I currently don't have any experience in accurately and safely storing their information in a constant database. This ability would be nice for personalizing this game to the player's top scores, as well as for countless features for other web development projects. 
* I would also like to know what are the best approaches for designing and aligning elements on a webpage. I know of Bootstrap but I’m afraid my knowledge is just around surface level. So I was wondering, on top of what tools to use, what the best practices are and what I should consider when designing a webpage or even mobile app? 


4. **If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words)**    
* If I had a few more hours, I would implement a feature that allows the user to pick a button using their keyboards. This could work by mapping the numbers (or any key that users could intuitively associate with a particular button) on the keyboard to one of the four buttons (btn). This will enable users to not have to use the mouse if they choose not to, since repeated tasks like this can be annoying or even unhealthy on a computer mouse or trackpad.       
* Another feature I would implement would be to add a background music option that would play music as soon as the player hits the Start button and ends when the stopGame() function is called. The music would create a more immersive game experience, as well as provide a little distraction from the sounds of the sequence to make the game more interesting (perhaps this feature would only be available in the Adv mode). 




## License

    Copyright Nhi Nguyen

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.