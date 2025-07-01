# Entity Component System - Legions

ECS or Enity Component System is a architecture for handling large amounts of game data.  ECS allows you to more easily share different components between different objects in your games logic.  

Parts of ECS
    - Entity
    - Component
    - Systems
    - Resources

An ECS in Rust is Legion which is what the code examples will be in.

## Entity

Entity can be an object like the Player, enemy, or a object like a book.  Entities don't have logic, but can be like an ID 

To create a new entity like a player just need to add as a struct.

```
struct player;
```

## Component

A component describes the property that the an entity can have. A player might have a position component, render component, Health component, and so on.  These don't have any logic either but just adds traits to the entity.

## System

Systems include the game logic to make the game function.  They query entities and them will perform task based on the components that the entities have like rendering the the screen, handling health, and so on.

## Resources

Resourecs are shared data available to multiple systems.

## Adding a player using Legions

Import the following into your logic

```
use legion::*;
use legion::world::SubWorld;
use legion::systems::CommandBuffer;
```

Push the player to an legions world object

```
fn add_player(ecs: &mut World) {
    ecs.push(
        (Player,
        Render {
            color: ColorPair::new(WHITE,BLACK),
            glyph: to_cp437('@')
        }
        )
    );
}
```

Then we can have a system that actually does the renering of the object to the screen.

