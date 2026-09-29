# 🎮 FourPlay

FourPlay is a Flutter implementation of the classic Connect Four board game. It is a two-player, turn-based game where players drop colored pieces into a 7-column × 6-row board and try to connect four pieces horizontally, vertically, or diagonally.

> **Project type:** Cross-platform Flutter mobile game.

## Gameplay

1. Choose a column.
2. Drop a piece into the selected column.
3. The piece occupies the lowest available position.
4. The turn switches to the other player.
5. The game checks for a winning sequence.
6. A full board without a winner produces a draw.
7. After a win or draw, the board resets.

### Winning Conditions
- Horizontal
- Vertical
- Diagonal

## Features

### Game
- 7 × 6 Connect Four board
- Two-player local gameplay
- Yellow vs. Red pieces
- Turn indicator
- Full-column validation
- Horizontal, vertical, and diagonal victory detection
- Draw detection
- Automatic reset after win/draw
- Exit confirmation during a game

### Additional Screens
- Dashboard with Start Game, How to Play, and Settings
- Rules/instructions screen
- Settings screen with theme, sound, and developer-information UI

## Game Logic

The game state is managed by a dedicated `GameController` using GetX.

```text
0 = Empty
1 = Yellow
2 = Red
```

The controller handles board initialization, turn switching, piece placement, full-board detection, victory checking, and reset behavior.

Victory checking evaluates four directions:

```text
→ Horizontal
↘ Diagonal
↗ Diagonal
↓ Vertical
```

## Project Structure

```text
FourPlay/
├── lib/
│   ├── controllers/
│   │   └── game_controller.dart
│   ├── core/bindings/
│   │   └── main_bindings.dart
│   ├── screens/
│   │   ├── dashboard.dart
│   │   ├── game_screen.dart
│   │   ├── how_to_play.dart
│   │   └── settings.dart
│   ├── utilities/
│   │   ├── buttons/
│   │   ├── game_screen_utilities/
│   │   ├── switch/
│   │   └── text/
│   └── main.dart
├── assets/
├── android/
├── ios/
├── pubspec.yaml
└── README.md
```

## Tech Stack
- Flutter
- Dart
- GetX for state management and navigation
- Material UI
- Android
- iOS

## Running Locally

Prerequisites: Flutter SDK and a configured Android/iOS development environment.

```bash
flutter pub get
flutter run
flutter doctor
```

## Current Limitations
- Local two-player only
- No online multiplayer
- No AI opponent
- No matchmaking
- No user accounts
- No persistent statistics or leaderboards
- Several Settings options are currently UI-only
- No automated gameplay test suite is currently implemented

## Possible Next Improvements
- AI opponent
- Online multiplayer
- Match history and persistent statistics
- Sound and theme persistence
- Piece-drop and win animations
- Automated unit tests for `GameController`

## Project Context

FourPlay was developed as a Flutter game project to practice mobile UI development, reactive state management, component decomposition, and implementation of board-game logic.