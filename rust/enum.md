# Enumerations

Enumerations is a type that contains a list of keywords.

## Declare a enum

```
enum GameState {
    Start,
    Playing,
    GameOver
}
```

Here is an enum of GameState.  By using enums we can set the current game state to one of the states defined in the enum and use it to perform the correct action.

```
match &self.state {
    GameState::Start => println!("Welcome to the game.  Press enter to start"),
    GameState::Playing => println!("Currently Playing),
    GameState::GameOver => println!("You are dead"),
}
```
