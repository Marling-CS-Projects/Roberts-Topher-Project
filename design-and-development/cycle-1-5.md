# 2.7 Cycle 6

## Design

### Objectives

set up power ups as well as a win loss system

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name | Use                                                                    |
| ------------- | ---------------------------------------------------------------------- |
| onCollide     | Show the anchor point of the Sprite                                    |
| Load Sprite   | Used to input what each symbol represents in the level                 |
| Area          | Collision detection (T/F)                                              |
| Body          | Static properties (T/F)                                                |
|               | Direction of movement                                                  |
| biggify       | Runs the function doubling the player in size for a set number of time |
| destroy       |                                                                        |
|               |                                                                        |

### Pseudocode

```




  
  
```

## Development&#x20;

### Outcome

```
function big() {
    let timer = 0
    let isBig = false
    return {
      update() {
        if (isBig) {
          CURRENT_JUMP_FORCE = BIG_JUMP_FORCE
          timer -= dt()
          if (timer <= 0) {
            this.smallify()
          }
        }
      },
      isBig() {
        return isBig
      },
      smallify() {
        this.scale = vec2(1)
        CURRENT_JUMP_FORCE = JUMP_FORCE
        timer = 0
        isBig = false
      },
      biggify(time) {
        this.scale = vec2(2)
        timer = time
        isBig = true     
      }
    }

"%": () => [
                sprite("star"),
                area(),
                body(),
                anchor("bot"),
                "star"
            ],        


player.onCollide("star", (s) => {
    {
            destroy(s)
    player.biggify(1)
       
    }
});


    player.onCollide("COIN", (c) => {
    {
        destroy(c)
        go("win")
       
    }
});
            
            
// Define the "win" scene
scene("win", () => {
    var jump = 1
add([
        text("You WIN"),
        pos(12),
    ]);
    // Press any key to go back to the start
    onKeyPress(start);
});

// Define the "lose" scene
scene("lose", () => {
    var jump = 1
    add([
        text("You Lose"),
        pos(12),
    ]);

    // Press any key to go back to the start
    onKeyPress(start);
});
```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th width="216">What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Interact with Star</td><td>the player is twice as large</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>interact with coin</td><td>Go win scene</td><td>As expected</td><td>Pass</td></tr><tr><td>3</td><td>Fall of map </td><td>Go lose scene </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

