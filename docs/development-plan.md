# Sleeping Queens Card Game - Development Plan

## Project Overview
A multiplayer online implementation of the Sleeping Queens card game using Node.js, Express, Socket.IO, and MongoDB. This project aims to create an engaging and interactive card game that can be played by multiple users in real-time.

## Architecture

### Backend
- **Node.js + Express**: Server framework that handles HTTP requests and responses, providing a robust environment for building the application.
- **MongoDB**: NoSQL database used for storing user data, game states, and other relevant information in a flexible and scalable manner.
- **Socket.IO**: Library for enabling real-time, bidirectional communication between clients and the server, essential for multiplayer interactions.
- **Passport**: Middleware for handling user authentication, allowing users to log in, register, and manage sessions securely.
- **EJS**: Templating engine used for rendering dynamic HTML pages on the server side.

### Frontend
- **Bootstrap**: UI framework that provides responsive design components, making the application visually appealing and user-friendly.
- **Socket.IO Client**: Library for enabling real-time updates on the client side, allowing users to receive game state changes instantly.
- **Vanilla JavaScript**: Used for implementing game logic and handling user interactions without relying on external libraries.
- **CSS3**: Custom styling applied to enhance the visual aspects of the application.

## Directory Structure
- Organized into separate folders for models, routes, services, views, and tests, ensuring a clean and maintainable codebase.

## Implementation Steps

### 1. Authentication System
- [] Initialize Node.js project: Create a new Node.js project using npm, setting up the package.json file to manage dependencies and scripts.
- [] Set up Express server: Configure the Express server to handle incoming requests, serve static files, and define API endpoints for the application.
- [] Configure MongoDB connection: Establish a connection to the MongoDB database, ensuring that the application can store and retrieve data as needed.
- [] Set up testing environment: Implement a testing framework (e.g., Jest) to facilitate unit and integration testing, ensuring code quality and reliability.
- [] Configure ESLint and Prettier: Set up ESLint for code linting to enforce coding standards and Prettier for code formatting to maintain a consistent style.
- [] Create User model with username and password fields: Define a Mongoose schema for the User model to manage user data, including validation rules.
- [] Add password hashing using bcrypt: Implement password hashing to securely store user passwords in the database, protecting against unauthorized access.
- [] Install and configure passport-local strategy: Set up Passport with the local strategy for username/password authentication, allowing users to log in securely.
- [] Implement serialize/deserialize user functions: Define functions to serialize and deserialize user instances for session management, enabling persistent user sessions.
- [] Create login.ejs view with Bootstrap styling: Design the login page using EJS and Bootstrap for a responsive layout, ensuring a user-friendly experience.
- [] Create register.ejs view with Bootstrap styling: Design the registration page similarly to the login page, allowing new users to create accounts easily.
- [] Implement /login route: Create a route to handle login requests, authenticate users, and manage session creation.
- [] Implement /register route: Create a route to handle user registration, validate input, and save new users to the database.
- [] Implement /logout route: Create a route to handle user logout, terminating the session and redirecting users to the login page.
- [] Add middleware for protected routes: Implement middleware to restrict access to certain routes for authenticated users only, enhancing security.
- [] Configure session store: Set up a session store to manage user sessions effectively, ensuring that session data is stored securely.
- [] Add session middleware: Integrate session middleware into the Express application to handle user sessions and maintain state across requests.
- [] Implement session cleanup: Define a mechanism to clean up expired sessions from the session store, optimizing resource usage.
- [] Allow guest players to join without registration: Create a temporary user session for guest players, allowing them to play without creating an account.
- [] Update login.ejs to include a "Play as Guest" button.
- [] Modify the /login route to handle guest logins, creating a temporary session for guest players.

### 2. Game Lobby
- [] Create Game model with Mongoose schema: Define a Mongoose schema for the Game model to manage game data, including players, cards, and game state.
- [] Implement game initialization methods: Create methods to initialize a new game, including setting up players, shuffling cards, and defining game rules.
- [] Create game service for core logic: Develop a service layer to encapsulate the core game logic, managing game state and player interactions.
- [] Add player management functions: Implement functions to manage player actions, including joining and leaving games, and tracking player status.
- [] Implement turn system: Define the rules for player turns, including how turns are passed and actions taken during a turn.
- [] Configure Socket.IO for real-time communication: Set up Socket.IO to enable real-time updates and interactions between players, ensuring a smooth gaming experience.
- [] Add event handlers for game actions: Implement event handlers to respond to player actions (e.g., drawing cards, playing cards) and update the game state accordingly.
- [] Implement room management socket events: Create socket events to manage game rooms, including creation, joining, and leaving, facilitating multiplayer gameplay.
- [] Implement room management: Define the logic for managing game rooms, including player lists, game states, and room lifecycle events.
- [] Add card drawing and playing logic: Implement the rules for drawing cards and playing them during the game, ensuring adherence to game mechanics.
- [] Implement queen capturing logic: Define the rules for capturing queens and how they affect the game state, including point calculations.
- [] Add special card effects: Implement the effects of special cards and how they interact with the game mechanics, enhancing gameplay variety.
- [] Implement win condition checking: Define the conditions for winning the game and how they are evaluated, determining when a player has won.
- [] Create matchmaking queue system: Develop a system to match players into games based on availability and skill level, optimizing player experience.
- [] Add player pairing logic: Implement logic to pair players in a game, ensuring a balanced experience and fair competition.
- [] Implement game room creation: Define the process for creating new game rooms and initializing game states, allowing players to start new games.
- [] Create game board UI: Design the user interface for the game board, displaying cards and player information.
- [] Add player hand display: Implement a visual representation of each player's hand of cards, allowing players to see their available actions.
- [] Implement card interaction: Define how players can interact with their cards and the game board, including playing cards and drawing new ones.
- [] Add game status display: Create a visual display of the current game status, including turn information, player actions, and game progress.

### 3. Game Core
- [] Create Game model with Mongoose schema: Define a Mongoose schema for the Game model to manage game data, including players, cards, and game state.
- [] Implement game initialization methods: Create methods to initialize a new game, including setting up players, shuffling cards, and defining game rules.
- [] Create game service for core logic: Develop a service layer to encapsulate the core game logic, managing game state and player interactions.
- [] Add player management functions: Implement functions to manage player actions, including joining and leaving games.
- [] Implement turn system: Define the rules for player turns, including how turns are passed and actions taken during a turn.
- [] Configure Socket.IO for real-time communication: Set up Socket.IO to enable real-time updates and interactions between players.
- [] Add event handlers for game actions: Implement event handlers to respond to player actions and update the game state accordingly.
- [] Implement room management socket events: Create socket events to manage game rooms, including creation, joining, and leaving.
- [] Implement room management: Define the logic for managing game rooms, including player lists and game states.
- [] Add card drawing and playing logic: Implement the rules for drawing cards and playing them during the game.
- [] Implement queen capturing logic: Define the rules for capturing queens and how they affect the game state.
- [] Add special card effects: Implement the effects of special cards and how they interact with the game mechanics.
- [] Implement win condition checking: Define the conditions for winning the game and how they are evaluated.

### 4. Game Features
- [] Card management: Implement functionality for managing the deck of cards, including shuffling and drawing.
- [] Turn system: Define the rules for player turns, including how turns are passed and actions taken during a turn.
- [] Queen capturing: Implement the rules for capturing queens and how they affect the game state.
- [] Special card effects: Define the effects of special cards and how they interact with the game mechanics.
- [] Game state management: Implement functionality to manage the overall state of the game, including active players and game progress.
- [] Win condition checking: Define the conditions for winning the game and how they are evaluated.

### 5. User Interface
- [] Design game board: Create a visually appealing design for the game board that enhances user experience.
- [] Implement card animations: Add animations for card movements and interactions to make the game more engaging.
- [] Add game chat: Implement a chat feature for players to communicate during the game.
- [] Create lobby system: Develop a lobby system for players to wait and prepare before starting a game.
- [] Add player statistics: Implement functionality to track and display player statistics, such as wins and losses.
- [] Create leaderboard: Develop a leaderboard to showcase top players and their achievements.

### 6. Admin Features
- [] Admin dashboard: Create a dashboard for administrators to manage the game and monitor player activity.
- [] User management: Implement functionality for administrators to manage user accounts and permissions.
- [] Game monitoring: Develop tools for monitoring ongoing games and player interactions.
- [] System statistics: Implement functionality to track system performance and user engagement metrics.
- [] Maintenance tools: Create tools for performing maintenance tasks on the game server and database.

### 7. Testing
- [] Unit tests for authentication system: Develop unit tests to ensure the authentication system functions correctly.
- [] Unit tests for Game model: Create unit tests for the Game model to validate its behavior and data integrity.
- [] Integration tests for game mechanics: Implement integration tests to verify that game mechanics work as intended.
- [] Socket.IO tests: Develop tests for Socket.IO functionality to ensure real-time communication is reliable.
- [] Load testing: Implement load testing to evaluate the performance of the application under heavy usage.
- [] Security testing: Conduct security testing to identify and address vulnerabilities in the application.

### 8. Deployment
- [] Set up production environment: Configure the production environment for hosting the application.
- [] Configure environment variables: Set up environment variables for sensitive information and configuration settings.
- [] Set up logging: Implement logging to track application activity and errors in production.
- [] Add monitoring: Set up monitoring tools to track application performance and health.
- [] Deploy to hosting platform: Deploy the application to a hosting platform for public access.

## Game Rules

### Setup
- 2-5 players
- Each player starts with 5 cards
- 12 queens are placed face-up in the center

### Card Types
1. **Number Cards (1-10)**
   - Used for drawing new cards
   - Can be played in combinations

2. **Power Cards**
   - King: Wake up a sleeping queen
   - Knight: Steal a queen from another player
   - Dragon: Block a knight's attack
   - Magic Wand: Block a knight's attack
   - Sleeping Potion: Put another player's queen back to sleep
   - Jester: Draw an extra card next turn

3. **Queens**
   - Different point values
   - Special abilities
   - Victory conditions

### Special Queens
- Rose Queen & Cat Queen: Double points when together
- Dog Queen: Protects adjacent queens
- Rainbow Queen: Counts as extra queen for victory

### Winning
- Collect 4 queens OR
- Reach 50 points

## Security Considerations
- Input validation
- Rate limiting
- Session management
- CSRF protection
- XSS prevention
- Socket authentication
- Error handling

## Performance Optimization
- Database indexing
- Caching strategies
- Connection pooling
- Asset optimization
- Load balancing

## Monitoring
- Error logging
- Performance metrics
- User analytics
- Game statistics
- System health

## Future Enhancements
- Mobile responsiveness
- AI opponents
- Tournament system
- Friend system
- Achievements
- Custom card skins

## Additional Implementation Details
### Guest Player Functionality
- [] Implement a "Play as Guest" button on the login page.
- [] Create a temporary user session for guest players, storing their game state in memory.
- [] Ensure guest players can join existing games and interact with other players.
- [] Provide an option for guest players to register for an account after the game.

### Game Initialization
- [] Define a method to reset the game state when a new game is started.
- [] Ensure that all players, including guests, are properly initialized in the game state.

### Real-time Updates
- [] Use Socket.IO to broadcast game state changes to all connected clients, ensuring that all players see the same game state in real-time.
- [] Implement event listeners for player actions to update the game state accordingly.

### Error Handling
- [] Implement error handling for all routes and socket events to ensure a smooth user experience.
- [] Log errors to the server console and provide user-friendly messages to clients.

### Testing Strategy
- [] Develop a comprehensive testing strategy that includes unit tests, integration tests, and end-to-end tests to ensure the application functions as expected.
