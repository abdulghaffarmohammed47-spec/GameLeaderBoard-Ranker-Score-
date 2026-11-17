# GameLeaderBoard Ranker Score

A Java console game and player leaderboard built to demonstrate data structures
and algorithms. Register players, play coin-based battle rounds, and compare
player rankings.

## Features

- Register up to 20 players; each starts with 500 coins.
- Play a number-guessing battle, spend coins on a shield, and save player
  progress.
- View the top three players or the full leaderboard.
- Search players by ID, delete a player, and undo the most recent deletion.
- View recent activity and the tournament roster for the current run.
- Rank players by coin balance using a max-priority queue.

## Data structures and algorithms

- **Hash table with separate chaining** for player lookup by ID.
- **Linked lists** for player records, recent activity, and the tournament
  roster.
- **Max heap / priority queue** for ranking players.
- **Heap sort** for displaying the leaderboard.
- **Stack** for undoing the most recent player deletion.

## Build and run

The Java sources are included in
[GameLeaderBoard(Ranker Score).zip](https://github.com/abdulghaffarmohammed47-spec/GameLeaderBoard-Ranker-Score-/blob/main/GameLeaderBoard%28Ranker%20Score%29.zip).
Install a JDK (version 8 or newer), download and extract the archive, then run
these commands from the extracted source directory:

```powershell
javac -d out *.java
java -cp out project.GamerLeaderBoard
```

The program creates `gameLeaderBoard.txt` in the current working directory and
stores each player's ID, name, and coin balance there. Run the program from the
same directory on later sessions to load the saved players.

## Other project in this repository

This repository also contains the separate Python/Flask **AlgoScholar**
research-paper discovery app. See [ALGOSCHOLAR.md](./ALGOSCHOLAR.md) for its
features and setup instructions.
