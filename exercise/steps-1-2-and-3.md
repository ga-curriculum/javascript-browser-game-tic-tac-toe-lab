# ![JavaScript Browser Game - Tic-Tac-Toe Lab - Exercise Steps 1, 2, and 3](./assets/hero.png)

## Step 1

**Define the required variables used to track the state of the game.**

> 💡 None of these variables will need to hold a value when they are defined.

a. Use a variable named `board` to represent the state of the squares on the board.

b. Use a variable named `turn` to track whose turn it is.

c. Use a variable named `winner` to represent if anyone has won yet.

d. Use a variable named `tie` to represent if the game has ended in a tie. 

## Step 2

**Store cached element references.**

a. In a constant called `squareEls`, store the nine elements representing the squares on the page.

   > 💡 Notice how each square has a matching class name in your HTML to make this easier!

b. In a constant called `messageEl`, store the element that displays the game's status on the page.

   > 🚨 Don't forget to `console.log()` your cached element references to ensure you've grabbed the correct elements!

## Step 3 

**Upon loading, the game state should be initialized, and a function should be called to render this game state.**

a. Create a function called `init`.

b. Call the `init` function when the app loads.

   > 🚨 Add a `console.log()` as a confirmation check inside this function. This helps to ensure you're calling the function you just created correctly!

c. Set the `board` variable to an array containing nine empty strings (`''`) representing empty squares.

   > 💡 The nine elements in the `board` array will correspond to a square on the board.
   > Index 0 (`board[0]`) will represent the top-left square.
   > Index 1 (`board[1]`) will represent the top-middle square.
   > Index 2 (`board[2]`) will represent the top-right square.
   > Index 3 (`board[3]`) will represent the middle-left square.
   > So on, continuing through the entire board until…
   > Index 8 (`board[8]`) will represent the bottom-right square.

d. Set the `turn` to `X` - this will represent player X.

   > 💡 Player O will be represented by `O`.

e. Set the `winner` to `false`.

   > 💡 A `false` value in `winner` means that there is no winner yet.
   > A value of `true` in `winner` will mean that a player has won. 
   >
   > Once `winner` is set to `true`, we can determine which player won by whose turn it was when the winning move was played.

f. Set `tie` to `false`.

   > 💡 A `true` value in `tie` will mean that the board array contains no more empty strings (`''`) and will be used to render a tie message if `winner` is still `false` by the time all squares are played.

g. Call a function named `render()` at the end of the `init()` function.

   > 🚨 This will throw an error until you complete step 4a!
