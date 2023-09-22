# 2.3 Movement and Collision

## Design

### Objectives

Set up environment for the Player

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name       | Use                                                    |
| ------------------- | ------------------------------------------------------ |
| Set Gravity         | Sets the constant downward acceleration                |
| Set Speed           | Sets  Movement speed                                   |
| constant add player | Add player into the environment                        |
| Anchor              | Show the anchor point of the Sprite                    |
| Load Sprite         | Used to input what each symbol represents in the level |
| Area                | Collision detection (T/F)                              |
| Body                | Static properties (T/F)                                |

### Pseudocode

```
Import Kaboom

Set Gravity:
Set Speed:

Load Sprite(Player)

constant add player
sprite(player)
area
body
anchor



  
  
```

## Development&#x20;

### Outcome

```
  onKeyPress("space", () => {
    if (player.isGrounded()) {
      player.jump();
    }
  });

  onKeyDown("left", () => {
    player.move(-SPEED, 0);
  });

  onKeyDown("right", () => {
    player.move(SPEED, 0);
  });

```

### Challenges

setting a speed value that makes platforming smooth and movment feel responsive

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    | Input Left   | Move left     | Move left             | Pass      |
| 2    | Input Right  | Move Right    | Move Right            | Pass      |
| 3    | Input space  | Move up       | Move up               |           |

### Evidence

