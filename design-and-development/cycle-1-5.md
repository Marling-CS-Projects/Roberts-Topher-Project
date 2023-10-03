# 2.7 Cycle 6

## Design

### Objectives

set up power ups as well as a win loss system

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name | Use                                                    |
| ------------- | ------------------------------------------------------ |
| onCollide     | Show the anchor point of the Sprite                    |
| Load Sprite   | Used to input what each symbol represents in the level |
| Area          | Collision detection (T/F)                              |
| Body          | Static properties (T/F)                                |
| dir           | Direction of movement                                  |

### Pseudocode

```




  
  
```

## Development&#x20;

### Outcome

```
"%": () => [
                sprite("star"),
                area(),
                body(),
                anchor("bot"),
                "star"
            ],        




player.onCollide("star", (s) => {
    {
        score = score + 1
        jump = jump + 1
        destroy(s)
       
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

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th>What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Interact with Star</td><td>player can jump twice</td><td>player can only jump twice once the scene changes</td><td>Fail</td></tr><tr><td>2</td><td>interact with coin</td><td>Go win scene</td><td>As expected</td><td>Pass</td></tr><tr><td>3</td><td>Fall of map </td><td>Go lose scene </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

