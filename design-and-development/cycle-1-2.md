# 2.4 Enemies

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
| onKeyPress          | Reads external input                                   |

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
 function patrol(speed = 60, dir = 1) {
  return {
    id: "patrol",
    require: ["pos", "area"],
    add() {
      this.on("collide", (obj, col) => {
        if (col.isLeft() || col.isRight()) {
          dir = -dir;
        }
      });
    },
    update() {
      this.move(speed * dir, 0);
    },
  };
}
//

      "*": () => [
        sprite("bad guy"),
        area(),
        body(),
        patrol(),
        anchor("bot"),
        "enemy",
        
//

```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

| Test | Instructions           | What I expect           | What actually happens | Pass/Fail |
| ---- | ---------------------- | ----------------------- | --------------------- | --------- |
| 1    | Input Left             | Move left               | As expected           | Pass      |
| 2    | Input Right            | Move Right              | As expected           | Pass      |
| 3    | Input space            | Move up                 | As expected           |           |
| 4    | Input space (airborne) | Move up while air born  | As expected           |           |

### Evidence

