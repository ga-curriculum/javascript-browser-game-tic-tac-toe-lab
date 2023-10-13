# Tic-Tac-Toe Lab - Lab Exercise Steps 6 and 7

![Hero image](./assets/hero.png)

## Step 6 

**Handle a player clicking a square with a `handleClick` function.**

a. Create a function called `handleClick`. It will have an `evt` parameter.

b. Attach an event listener to the game board. You can take one of two approaches to this (you can do this to each one of the existing `squareEls` with a  loop OR add a new cached element reference that will allow you to take advantage of event bubbling). On the `'click'` event, it should call the `handleClick` function you created in step 6a.

   > 💡 If you use the event bubbling method above, you'll need to make sure the element that the user clicks is actually a square! If they click anywhere else on the board, `return` out of the function to disallow the move. This can be accomplished more easily once you obtain the index of the square clicked in the next step!

c. Obtain the index of the square that was clicked by extracting the index from an `id` assigned to the target element in the HTML. Assign this to a constant called `sqIdx`.

  > 💡 Each `id` corresponds with an index in our `board` array.

d. If the `board` has a value of `-1` or `1` at the `sqIdx` position, immediately `return` out of `handleClick`.That square is already taken. Also, if `winner` is `true`, immediately `return` out of `handleClick` because the game is over.

Next, we will be creating a collection of smaller functions to break down the remaining functionality of our `handleClick` function. These functions will live in the global scope, and be invoked in a specific order inside of our `handleClick` function: 

### 6.1 - `placePiece`

a. Create a function named `placePiece` that accepts an `index` parameter.

b. Update the `board` array at the `index` so that it is equal to the current value of `turn`.

   > 💡 For testing purposes, on the line immediately after you've updated the board array, add a console log of the `board` array. 

c. In the `handleClick` function call the `placePiece` function you just created. Pass `sqIdx` to it as an argument.

   > 💡 If you added a console log above, you should now be able to click spaces on the board and the corresponding space in the `board` array should change from a `0` to a `1`. 

### 6.2 - `checkForWinner`

a. Create a function called `checkForWinner`.

b. Determine if a player has won using one of the two options below. 

   **Option 1** is a more elegant method that takes advantage of the `winningCombos` array you wrote above in step 5. 
   
   **Option 2** might be a little simpler to comprehend, but you'll need to write more code. This option won't take advantage of the `winningCombos` array, but using it as a reference will help you build a solution.

   ***Ensure you choose only one path.***

- **Option 1:** Loop through each of the winning combination arrays defined in the `winningCombos` array. 
  
  Total up the value of the three `board` positions using the three values in the current combo as indexes to access three different positions in the `board` array. 
  
  Convert the total to an absolute value (convert any negative total to positive). 
  
  If the total equals 3, we have a winner, and can set `winner` to `true`.

- **Option 2:** You'll use the winning combinations you wrote in step 5, and the `board` array. 

  Use the three values in each winning combination to retrieve the values held in those index positions of the `board` array. 

  For example, the first winning combination is `[0, 1, 2]` represents the top row. Using that winning combination as a guide, you know you'll need to access the values held in the `0`, `1`, and `2` index of the `board` array. 

  Add the values held in those positions of the board array together.

  Convert the total to an absolute value (convert any negative total to positive). 

  You'll do this for each of the winning combos.

  If the total of any of the combinations equals 3, we have a winner, and can set `winner` to `true`.

c. In the `handleClick` function call the `checkForWinner` function immediately after calling the `placePiece` function.

   > 💡 This function's only job is to determine if there is a winner. For testing purposes, after you've updated the `winner` state add a console log for `winner`.
   >
   > If you click every space that makes up a single winning combination (for example, the top row) on the board, `winner` should become `true`.

### 6.3 - `checkForTie`

a. Create a function named `checkForTie`.

b. Check if there is a winner. If there is, return out of the function.

c. Check if the `board` array still contains any elements with a value of `0`. If it does, we can leave `tie` as false. Otherwise, set `tie` should be set to true.

   > 💡 For testing purposes, after you've updated the `tie` state, add a console log for `tie`.

d. In the `handleClick` function call the `checkForTie` function immediately after calling the `checkForWinner` function.

   > 💡 This function's only job is to determine if all available moves have been played.
   >
   > If you click every space on the board so that the `board` array no long has any `0`s in it, `tie` should become `true`.

### 6.4 - `switchPlayerTurn`

a. Create a function called `switchPlayerTurn`.

b. If `winner` is true, return out of the function - we don't need to switch the turn anymore because the person that just played won!

c. If `winner` is false, change the turn by multiplying `turn` by `-1` (this flips a `1` to `-1`, and vice-versa).

   > 💡 For testing purposes, after you've updated the `turn` state, add a console log for `turn`.

d. In the `handleClick` function call the `switchPlayerTurn` function immediately after calling the `checkForTie` function.

   > 💡 This function's only job is to switch the turn after a player has made a selection and didn't win.
   >
   > If you click a space on the board, `turn` should flip from `1` to `-1` or flip from `-1` to `1`.

### 6.5 - Tying it all together

a. Finally, now that all the state has been updated we need to render that updated state to the user by calling the `render` function that we wrote earlier.


> 💡 Remember, we are using `render` to call upon two other functions (`updateBoard` and `updateMessage`). Both of these functions deal with updating different aspects of the user interface. 
> 
> Technically, the code in each of these functions could be moved directly inside `render`, but it makes sense to divide this logic based on the area of the user interface being altered. 
> 
> Ideally, your individual functions should accomplish as specific a task as possible.

## Step 7 - Create Reset functionality

a. Add a reset button to the HTML document.

b. Store the new reset button element as a cached element reference in a constant named `resetBtnEl`.

c. Attach an event listener to the `resetBtnEl`. On the `'click'` event it should call the `init` function you created in step 3.

> 💡 You’re done! As a final step, always be sure to test the game out to ensure everything is working as expected. Consider edge cases, and use console logs to investigate your code if anything is behaving oddly.
