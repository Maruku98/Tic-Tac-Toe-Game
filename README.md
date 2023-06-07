# Tic Tac Toe Game 🎮
Download this project and play Tic Tac Toe with your friends! But don't get mad at them 🤣

<img src="https://github.com/Maruku98/Tic-Tac-Toe-Game/assets/133391272/5c7563f5-4678-4dc1-a34f-7f1482b5c088" height="500"> <br></br>
## Overview
Although being a simple project, it really helped me grasp plenty of basic concepts about logical programming.

## PROGRAMMING LANGUAGES USED
- **HTML5**
- **CSS3**
- **JavaScript ES6**
- **React**
- **Node.js** (to build the app)

## GAME LOGIC

Below you'll find the logic behind my game 🕹️

### BOARD
- 9 button components are created from an empty `array` using the method `array.map()`.
- The `innerText` property of each button is changed upon clicking on them. This action is only triggered if the button value is empty to prevent overriding.
- The process is handled by the function `turnChange`.
- There are two buttons available to the user-- one to reset the game and another to reset the score.
- ⚠️To access `innerText` property, I needed to create a `nodeList` first. However, since JavaScript created it *before* React could render the components to the page, this triggered an error on first load since `nodeList` was empty. SOLUTION: asynchronous code! A promise is called to create the `nodeList` with a 10 milliseconds delay.

### GAME STATES
The App uses several `useState` and one `useEffect` to manage the gameplay
  - Player turns are handled by `useState` `turnState`.
  - A winner is detected with `useState` `winner`.
  - Draw is detected (no player wins) with `useState` `draw`.
  - Two more `useState` control `X` and `O` scores. `useEffect` increments player's score by one depending on the `winner` value.

### CONDITIONAL RENDERING
The game relies on conditional CSS rendering to show or hide different elements after the game ends
  - Header color changes according to player color-- blue for `O`, orange for `X`. Perhaps a Portal 2 reference? 🤔
  - Styles change whether one player wins or the game ends in a draw. This displays a text accordingly and hides all elements except the reset button.
 
### FUNCTIONS
- `turnChange` writes player mark on the board and changes player turn and styles accordingly.
- `checkDraw` checks if the game ends in a draw by changing the state of `draw` only when all buttons are not empty and there's no winner either.
- `checkwinner` checks if a player won on every turn by checking all possible win combinations in-place.
- `allFunctions` functions wraps all functions that are triggered at once when user a clicks a button.
- `resetGame` resets all values to their initial state.
- `resetScore` resets player score to 0.
