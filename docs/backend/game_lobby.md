# Game Lobby Implementation Plan

## Overview
This document outlines the steps required to implement the game lobby for the Sleeping Queens card game. The game lobby will display ongoing game sessions and provide users with the option to create new game sessions.

## Steps for Game Lobby Implementation

### 1. Create Game model
- **Action**: Define a Mongoose schema for the Game model.
- **Details**:
  - Create a `models` directory and a `Game.js` file.
  - Include fields for:
    - `players`: Array of player IDs currently in the game.
    - `gameState`: Enum to represent the current state of the game (e.g., waiting, in-progress).
    - `createdAt`: Timestamp for when the game was created.

### 2. Implement game session retrieval
- **Action**: Create a method to retrieve ongoing game sessions.
- **Details**:
  - Define a method to query the database for games with a state of "in-progress".
  - Return the list of ongoing games to be displayed in the lobby.

### 3. Create game session creation functionality
- **Action**: Implement functionality for users to create new game sessions.
- **Details**:
  - Create a form in the lobby UI for users to input game details (e.g., game name, player limit).
  - Define a method to create a new game session in the database.
  - Set the initial game state to "waiting" and add the creator as a player.

### 4. Display ongoing game sessions
- **Action**: Design the UI to display ongoing game sessions.
- **Details**:
  - Create a section in the lobby UI to list all ongoing games.
  - Include buttons for users to join existing games or create a new game session.

### 5. Implement join game functionality
- **Action**: Allow users to join ongoing game sessions.
- **Details**:
  - Define a method to add a player to an existing game session.
  - Update the game state and notify other players of the new participant.

### 6. Configure Socket.IO for real-time updates
- **Action**: Set up Socket.IO for real-time updates in the lobby.
- **Details**:
  - Install Socket.IO with `npm install socket.io`.
  - Configure Socket.IO on the server to handle connections and broadcast updates when a new game is created or a player joins.

### 7. Add event handlers for lobby actions
- **Action**: Implement event handlers for actions in the lobby.
- **Details**:
  - Create handlers for actions like creating a new game and joining an existing game.
  - Update the lobby UI in real-time to reflect changes in ongoing games.

### 8. Test the game lobby functionality
- **Action**: Conduct thorough testing of the game lobby.
- **Details**:
  - Ensure that users can see ongoing games, create new sessions, and join existing games without issues.
  - Gather feedback from users to identify areas for improvement.
