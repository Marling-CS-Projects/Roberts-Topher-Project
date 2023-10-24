# 2.8 Win/Loss setup

## esign

### Objectives

set up win loss system

* [x] Display when when conditions are met
* [x] Display a loss screen when the player dies

### Usability Features

### Key Variables

| Variable Name | Use                 |
| ------------- | ------------------- |
| destroy       | Destroys the object |

### Pseudocode

```

When the player collides with a "COIN":
    Destroy the coin.
    Transition to the "win" scene.

Define the "win" scene:
    Set jump to 1.
    Display the text "You WIN" at position (12).
    Wait for any key press to return to the start scene.

Define the "lose" scene:
   
    Display the text "You Lose" at position (12).
    Wait for any key press to return to the start scene.



  
  
```

## Development&#x20;

### Outcome

```

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


  
  
```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th width="216">What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>interact with coin</td><td>Go win scene</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>Fall of map </td><td>Go lose scene </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>
