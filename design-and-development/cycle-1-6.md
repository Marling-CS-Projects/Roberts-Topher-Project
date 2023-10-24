# 2.9 Menu setup

## Design

### Objectives

set up power ups as well as a win loss system

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name | Use                                             |
| ------------- | ----------------------------------------------- |
| Is paused     | Boolean value fot weather the menu is displayed |

### Pseudocode

```
  Define a boolean variable isPaused and set it to false.

Create a new scene called "pause":
  Display "Paused" text with size 48 at the center of the screen.
  When the "z" key is pressed:
    Set isPaused to false.
    Transition to the "game" scene.

Create a scene called "game":
  When the "z" key is pressed:
    Set isPaused to true.
    Transition to the "pause" scene.
```

## Development&#x20;

### Outcome

```
let isPaused = false;

// Create a new scene called "pause"
scene("pause", () => {
  add([
    text("Paused", {
      size: 48,
      pos: vec2(width() / 2, height() / 2),
      origin: "center",
    }),
  ]);

  onkeypress("z", () => {
    isPaused = false;
    go("game"); // Return to the "game" scene
  });
});

// Update the game scene to add pause functionality
scene("game", () => {
      onkeypress("z", () => {
    isPaused = true;
    go("pause"); // Go to the "pause" scene
  });
```



## Testing



### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th width="216">What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Press Z</td><td>the game to pause and the menu is displayed</td><td>Game pauses withouth menu</td><td>Fail</td></tr><tr><td>2 </td><td>Press Z while game is paused</td><td></td><td></td><td></td></tr></tbody></table>

### Evidence

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

