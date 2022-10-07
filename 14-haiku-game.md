#Haiku Game

## Overview

A round-robin Haiku maker.
Each player takes turns.
The first player supplies the first word of the Haiku
Each play, in turn adds one word to the Haiku until the Haiku finishes.
You can vote on finished Haikus. Finished haikus can climb up the leaderboard based on votes, and users get points for their Haikus.

## Details

There is server that keeps the state of the game for all the players.

The first step of the game is too join it.

In this stage, the players connect to the server, and give thier names.
The server keeps track of how many players have joined.
When 3 players have joined, it starts a game.

The next stage is the actual game play.
The server needs to keep track of anumber of things

* The names and sockets of all the players
* The unfinshed haiku as a double array. An array of lines and an array of words.
* Whose turn it is.
* If the haiku is finished or not.
* Which line of the haiku we are one.
* Also, it needs to check if the supplied word is valid.

Each turn, this information is passed to the clients who then can:

* see the last play.
* participate if it is their turn to play.


