# 2.2 Stage setup

## Design

### Objectives

Set up environment for the Player

* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name  | Use                                                    |
| -------------- | ------------------------------------------------------ |
| Load Sprite    | Imports sprite from data base                          |
| Tile Width     | width of the sprite                                    |
| Tile Height    | height the sprite                                      |
| Pos (position) | sets the position of the upper left block              |
| Tiles          | used to input what each symbol represents in the level |
| Area           | collision detection (T/F)                              |
| Body           | static properties (T/F)                                |

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
area
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

![](../.gitbook/assets/image.png)
