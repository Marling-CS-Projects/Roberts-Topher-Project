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

<table data-full-width="true"><thead><tr><th>Test</th><th>Instructions</th><th>What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Input Left</td><td>Move left</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>Input Right</td><td>Move Right </td><td>As expected</td><td>Pass</td></tr><tr><td>3</td><td>Input space</td><td>Move up </td><td>As expected</td><td>Pass</td></tr><tr><td>4</td><td>Input space (airborne)</td><td>Move up while air born </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence
