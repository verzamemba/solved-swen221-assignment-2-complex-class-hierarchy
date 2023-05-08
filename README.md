Download Link: https://assignmentchef.com/product/solved-swen221-assignment-2-complex-class-hierarchy
<br>
This assignment will expose you to a more complex class hierarchy. A key challenge will be in understanding the flow of control through the program, particularly as there is extensive use of polymorphism. This assignment will also test your debugging skills, and you should strive to be methodical in how you approach debugging.

<h1>Tetris</h1>

This assignment concerns the classic game of “Tetris”, originally developed by the Russian programmer Alexey Pajitnov. The tetris pieces (called <em>Tetromino</em>’s) are controlled using the keyboard (in this case, the arrow and space keys). As is usual in the game, the pieces are subject to “gravity” meaning that they slowly descend downwards. Pieces can be made to descend more quickly using either the <em>down arrow key </em>or much more quickly using the <em>space key</em>. Likewise, pieces move left or right, and rotate clockwise using the <em>up arrow key</em>. The code includes a graphical user interface so you can play it:

In Tetris, there are seven tetrominoes:

<h2>                                           “Z”          “S”            “T”           “J”           “L”         “O”          “I”</h2>

Each tetromino has an <em>axis of rotation </em>illustrated above using a circle and an <em>orientation </em>(i.e. <em>North, East, South, West</em>). The tetromino above are illustrated in their <em>North </em>orientation. Finally, for more information on the game of Tetris, refer to https://en.wikipedia.org/wiki/Tetris.

<h1>Getting started</h1>

To get started, download the tetris.jar file from the lecture schedule on the course website. As usual, you can run the program from the command-line as follows:

java -jar tetris.jar

A simple GUI should appear on your screen, and you should be able to play the game. <em>Remember, however, that at this stage the game contains a number of bugs and missing features. </em>For example, pieces move in the opposite direction from what you are expecting!

<h2><strong>Understanding the Code</strong></h2>

Each piece is implemented as a separate class which extends the abstract class Tetromino. When you import the tetris.jar file, you should find the following Java packages:

<ul>

 <li>The swen221/tetris/gui/ package contains the graphical user interface and the main method. <strong>You do not need to understand the inner workings of this in order to complete the assignment. NOTE: </strong>you do not need to modify any code in this package.</li>

 <li>The swen221/tetris/logic/ package contains the class Game encoding the logic of a game of Tetris, and the class Board representing the current state of the board.</li>

 <li>The swen221/tetris/tetromino/ package contains the interface Tetromino and the concrete implementations for all tetromino.</li>

 <li>The swen221/tetris/moves/ package contains a class for each of the different kinds of move that can be made in the game. These contain code related to structuring a move, and ensuring it is valid.</li>

 <li>The swen221/tetris/tests/ packages contains many jUnit tests to check your implementation of the game. <strong>NOTE: </strong>To make the automatic marking possible, you can not modify the files already present in this folder, but you may add your tests in a separate file (e.g. java).</li>

</ul>

<h1>Part 1 — Simple Moves</h1>

The first objective is to make sure the game correctly recognises all of the simple moves that a piece can make. Specifically, this part concerns mostly minor problems in the tetromino implementations (e.g. J Tetromino) and the RotationMove and TranslatioMove classes. At this stage more complex moves, such as for remove lines and ending the game, can be ignored. A suite of tests for this part is provided in swen221/tetris/tests/Part1Tests.java. You can run these tests individually, or all together. <strong>You are advised to write additional tests to ensure the system is working correctly.</strong>

<h1>Part 2 — Landings</h1>

The second objective is to implement the mechanism for <em>landing </em>pieces. In particular, this includes the “drop move” where a piece descends immediately from its current place. When a piece is landed, the next turn continues. A suite of tests is provided in swen221/tetris/tests/Part2Tests.java.

<h1>Part 3 — Invalid Moves</h1>

The third objective is to make sure the game correctly recognises when a move is invalid. For example, a piece cannot be moved off the side of the board. Likewise, a piece cannot be dropped below the bottom of the board, or into the middle of another piece. The following illustrates such a situation, where one piece is landed in the middle of two others:

(1)                                                              (2)

A suite of tests for this part is provided in swen221/tetris/tests/Part3Tests.java. You can run these tests individually, or all together. <strong>You are advised to write additional tests to ensure the system is working correctly.</strong>

<h1>Part 4 — Line Removal</h1>

The final objective is to correctly handle line removal rows when a tetromino has been “landed”. The following illustrates the a tetromino being landed and a number of full rows being removed:

(1)                                                               (2)                                                               (3)

Here, we see that <em>three full rows </em>are removed when the I tetromino is landed. A suite of tests for this part is provided in swen221/tetris/tests/Part4Tests.java