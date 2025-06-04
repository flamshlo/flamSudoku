# flamSudoku

Gemini according to specs 

flamSudoku is an interactive web-based Sudoku game that allows users to set up their own puzzles and then play them. It features a unique 9x9 grid where each cell contains a smaller 3x3 grid for detailed candidate tracking. The application provides real-time feedback on game progress, including error highlighting and summary views of rows, columns, 3x3 boxes and digits usage.

## Features

* **Custom Puzzle Setup (`NEW`/`SET` Mode):**

  * Initiate a new puzzle by clicking the "NEW" button.

  * Input initial fixed clues either by clicking on individual digits within the main grid cells or by typing a 27-digit string for each of the three main grid rows into the provided `textarea`.

  * The `textarea` input is validated for correct format (`XXX XXX XXX. XXX XXX XXX. XXX XXX XXX;` for lines 1-2, and `.` for line 3) upon pressing "SET".

  * Fixed clues are visually distinct (dark green background, unchangeable).

* **Interactive Gameplay:**

  * For editable cells, clicking on a digit cycles through three states:

    * **Possible (Light Green):** All 9 digits are visible, indicating potential candidates.

    * **Optionally Chosen (Pink):** A user-marked candidate for consideration.

    * **Definitely Chosen (Dark Green):** The confirmed solution for the cell. All other digits in the cell are grayed out.

* **Real-time Feedback & Error Highlighting:**

  * **Rows, Cols, and Boxes Summaries:** Dedicated summary grids for each row, column, and 3x3 box display the "definitely chosen" digits within their respective regions in bright green.

  * **Digit Count Summary:** A special 3x3 grid tracks the overall count of each digit (1-9) in the main puzzle:

    * **Light Gray:** Digit chosen less than 3 times.

    * **Blue:** Digit chosen more than 7 times but less than 9.

    * **Green:** Digit chosen exactly 9 times.

    * **Red:** Digit chosen more than 9 times (indicating an error).

  * **Duplicate Error Highlighting:** If a digit is "definitely chosen" more than once within a single row, column, or box, that digit in the corresponding summary cell will be highlighted in **red**.

* **Undo/Redo Functionality:**

  * "UNDO" allows reverting the last action (digit change in a cell).

  * "REDO" allows re-applying an undone action.

* **Restart Game:** The "RESTART" button reverts the game to the state saved when "SET" was last pressed, allowing you to replay the same puzzle.

* **Intuitive Interface:** Icon buttons for common actions enhance usability.

## How to Play

1. **Start a New Game:** Click the **NEW** button. It will change to **SET**.

2. **Set Up the Puzzle:**

   * **Option 1 (Clicking):** In the main 9x9 grid, click on the small digits (1-9) within a cell. Each click on a digit will toggle it as a "definitely chosen" clue for that cell. All other digits in that cell will be grayed out. Clicking the same digit again will unset it, making all digits in the cell "possible" again.

   * **Option 2 (Text Area):** Type your puzzle's initial configuration into the `textarea` above the grid. Each line represents three rows of the Sudoku grid, with '0' for empty cells and '1' through '9' for fixed clues. Ensure the format is strictly followed:

     ```
     000 000 000. 000 000 000. 000 000 000;
     000 000 000. 000 000 000. 000 000 000;
     000 000 000. 000 000 000. 000 000 000.
     
     
     
     ```

3. **Confirm Setup:** Once your initial puzzle is entered, click the **SET** button. If the `textarea` format is incorrect, an error message will appear, and you'll remain in SET mode to correct it. If valid, the puzzle is set, and the button reverts to "NEW".

4. **Play the Game:**

   * Click on any non-fixed cell's inner digit to cycle through its states:

     * **Possible (light green):** Default state, all candidates visible.

     * **Optionally Chosen (pink):** A potential candidate you're considering.

     * **Definitely Chosen (dark green):** Your confirmed solution for the cell. This will gray out other digits in the cell.

   * The "Rows", "Cols", "Boxes" summary grids, and the overall digit count grid will update in real-time, showing progress and highlighting any errors (duplicates or incorrect total counts).

5. **Use Controls:**

   * **RESTART:** Resets the game to the state saved when "SET" was last pressed.

   * **UNDO:** Reverts the last change made to a cell.

   * **REDO:** Re-applies an undone change.

   * **CALC:** (Functionality to be implemented)

## Technologies Used

* **HTML5:** For the basic structure of the web page.

* **CSS3:** For styling, layout (Grid and Flexbox), and visual feedback.

* **JavaScript (ES6+):** For all game logic, DOM manipulation, state management, and interactivity.

* **Font Awesome:** For the interactive button icons.

* **Google Fonts (Inter):** For a clean and modern typography.

## Future Enhancements

* Implement the "CALC" button functionality (e.g., for solving, checking validity, or providing hints).

* Add more sophisticated validation rules for Sudoku logic (e.g., preventing more than one definite choice per cell).

* Improve accessibility features.

* Add different difficulty levels for pre-generated puzzles.

* Implement local storage to save game progress.
