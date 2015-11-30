Connect-k

The Connect-k program was designed as a test bed for different AI techniques for playing Connect-k games family: Tic-Tac-Toe, Go-moku, Connect-6 etc. We attempted to develop general game playing algorithms capable of playing any game within the Connect-k family. As such, the interface is currently tailored toward debugging and testing rather than being user-friendly. The Connect-k program we produced is currently the only open source program to play Connect-6.

Year: 2007  Language: C# Original website: http://risujin.org/connectk/

![Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.](connectk1.jpg "Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.")

![Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.](connectk2.jpg "Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.")

The Connect-k family of games contains games defined by three parameters: k, p, and q. The game is played on a Go-style (but not necessarily size) board. There are two players, black and white, who take turn placing stones on the board. The first player (black) plays q stones on the first turn and each player then plays p stones on every succeeding turn. The first player to form a horizontal, vertical, or diagonal sequence of k stones wins.

The game family includes Tic-Tac-Toe, Go-moku without capture rules, and a new game, Connect-6. Connect-6 was formally introduced and analyzed by Dr. I-Chen Wu in a series of papers that attempted to show that the game is fair. This has not been decisively proven but appears to be the case.

The Connect-k program originated as a University of Minnesota undergraduate Artificial Intelligence course project for the Spring 2007 semester. Aside from me, the project group included Jeff Deitch, Gabe Emerson, and Erik Shimshock. We attempted to develop general game playing algorithms capable of playing any game within the Connect-k family. The Connect-k program we produced is currently the only open source program to play Connect-6.

Download

Connect-k is built with the cross-platform GTK+ library and is distributed for Linux and Windows under the terms of the GPL.

Linux

Connect-k was developed on Debian Linux. On Debian-based systems you will need to install the latest libgtk2.0-dev and libcairo2-dev packages. Download and extract the source tarball and run ./configure & make to compile the program. The tarball was made with Autotools so it supports the usual Makefile targets.

Windows

Connect-k compiles and runs on Windows. However, because it uses the GTK+, you will need the GTK+ runtime environment for Windows installed. Once you have installed the runtime files, you can download the Windows binaries from the link above, unzip, and run the program

If you wish to compile in Windows, I have provided a Microsoft Visual Studio 2003 solution file for the source, located in the win32 folder of the source tarball. You will need to setup the GTK+ SDK for Windows for use with your compiler. You may end up downloading quite a few modules from that page. Unzip them all into the same folder and set the correct includes/library paths for your compiler.

AI overview

The Connect-k program was designed as a test bed for different AI techniques for playing the game. As such, the interface is currently tailored toward debugging and testing rather than being user-friendly. The screenshots in this section show the Black's potential moves as seen by the AI. Every move considered is marked with a color from blue to red, representing increasing desirability.

Threats

The Threats utility function, even without searching, provides a strong opponent to intermediate players. The AI tailored to find moves that will build multiple sequences or build a sequence and block an opponent's sequence. In this screenshot, the AI favors extending Black's two sequences of 3.

This utility function does fail on one major point. By extending the largest available sequence, it is acting in a greedy fashion. By planning ahead, an expert human player can take advantage of this weakness.

![Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.](threats.jpg "Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.")

Sequences

Sequences is the most challenging utility function. Even without search it can be a difficult opponent for an moderately skilled player. It is prefers to build up board configurations that develop into advantageous configurations later in the game by giving disproportionate utility to shorter sequences.

In this screenshot, the AI prefers to build up multiple available lines for future moves rather than extend Black's 3-sequences. This utility function is interesting because it produces behavior that would normally be expected of requiring extensive lookahead without doing any searching at all.

The Sequences AI was developed by Jeff Deitch.

![Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.](sequences.jpg "Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.")

Monte Carlo

The Monte Carlo AI is inspired by previous efforts to apply simulated annealing to playing the game of Go. We adapted this technique to play Connect-k. After generating a small list of promising moves using one of the above utility functions, a number of games are played for each resulting board with successive moves determined randomly. The position which results in the greatest number of won boards for the current player is chosen.

The Monte Carlo AI plays fairly well but spends a considerable amount of time choosing a move. In a sense this technique is a brute-force attempt to find a good move and is complicated by the large state space. In this screenshot, although very few moves were analyzed, the AI will recommend the same move as Sequences.

The Monte Carlo AI was developed by Jeff Deitch.

![Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.](montecarlo.jpg "Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.")

Tags: Five in a Row, Tic Tac Toe, TicTacToe, 5 in a Row, Go-Moku, Connect, Connect5, Connect6, Caro, Noughts and Crosses, Gomoku, Renju, Pente, Piskvork, Amoba, Kó³ko i Krzy¿yk, Gomocup, AI, Engine, Artificial Intelligence, Brain, Pbrain, Gra, Game, Source Code Files, Program, Programming, Github, Board, Coding.
