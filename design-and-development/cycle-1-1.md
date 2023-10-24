# 2.3 Movement

## Design

### Objectives

Set up environment for the Player

* [x] Set up reletive speed and gravity
* [x] Add colision and controls for the player

### Usability Features

### Key Variables

<table><thead><tr><th width="275">Variable Name</th><th>Use</th></tr></thead><tbody><tr><td>Set Gravity</td><td>Sets the constant downward acceleration</td></tr><tr><td>Set Speed</td><td>Sets  Movement speed</td></tr><tr><td>constant add player</td><td>Add player into the environment </td></tr><tr><td>Anchor</td><td>Show the anchor point of the Sprite</td></tr><tr><td>Load Sprite</td><td>Used to input what each symbol represents in the level</td></tr><tr><td>Area</td><td>Collision detection (T/F)</td></tr><tr><td>Body</td><td>Static properties (T/F)</td></tr><tr><td>onKeyPress</td><td>Reads external input</td></tr></tbody></table>

### Pseudocode

```
Function for the Player:
    Create a player sprite
    Define an area for the player
    Add a body to the player
    Set the anchor point to the bottom of the player sprite
    Assign the label "player" to the player

    When the "space" key is pressed:
        If the player is on the ground:
            Make the player jump

    When the "left" key is held down:
        Move the player to the left with a speed of SPEED

    When the "right" key is held down:
        Move the player to the right with a speed of SPEED
  
  
```

## Development&#x20;

### Outcome

```
  "@": () => [
        sprite("player"),
        area(),
        body(),
        anchor("bot"),
        "player",
        
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

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="152">Test</th><th>Instructions</th><th>What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Input Left </td><td>Move left</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>Input Right</td><td>Move Right </td><td>As expected</td><td>Pass</td></tr><tr><td>3</td><td>Input space</td><td>Move up </td><td>As expected</td><td>Pass</td></tr><tr><td>4</td><td>Walk over platform</td><td>Player collides with the platforms</td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

![](<../.gitbook/assets/image (13).png>)

