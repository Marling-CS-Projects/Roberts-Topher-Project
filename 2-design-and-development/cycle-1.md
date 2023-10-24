# 2.2 Stage setup

## Design

### Objectives

Set up environment for the Player

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name        | Use                                                                    |
| -------------------- | ---------------------------------------------------------------------- |
| kaboom               | Import of the Kaboom library, which simplifies game development        |
| loadSprite           | Function for loading game sprites with associated names and file paths |
| setGravity           | Function for setting the gravity force in the game                     |
| scene                | Function for defining and managing game scenes                         |
| Tile width / height  | Sets the size of the tiles                                             |
| Body                 | Eneables collision of the object                                       |

### Pseudocode

<pre><code>Import Kabooom

Load Sprite(Floor)

Add Level (
<strong>  "    ==     ",
</strong>  "===    ==  ",
  "           ",)
  
tile Width
tile Height
pos

tiles (=)
Sprite(Floor)
body

  
  
</code></pre>

## Development&#x20;

### Outcome

```html
loadSprite("Floor", "sprites/Floor.png");

const LEVELS = addLevel([
  ["    ==        ",
   "===    ==     ",
   "           == ",
  ],
  
  tileWidth: 50,
  tileHeight: 50,
  
  pos: vec2(100, 200),
  
  tiles: {
      "=": () => [
        sprite("Floor"),
        area(),
        body({ isStatic: true }),
       }

```

### Challenges

Description of challenges

## Testing

### Tests

<table data-full-width="true"><thead><tr><th>Test</th><th>Instructions</th><th>What I expect</th><th width="227.2">What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Run code</td><td>Grass blocks appear and collide with player</td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

![](<../.gitbook/assets/image (1) (2).png>)
