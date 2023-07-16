# 2.2.1 Stage setup

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

```
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
        sprite("player"),
        area(),
        body({ isStatic: true }),
       }

```

### Challenges

Description of challenges

## Testing



Evidence for testing

### Tests

| Test | Instructions  | What I expect     | What actually happens | Pass/Fail |
| ---- | ------------- | ----------------- | --------------------- | --------- |
| 1    | Run code      | Thing happens     | As expected           | Pass      |
| 2    | Press buttons | Something happens | As expected           | Pass      |

### Evidence

![](../.gitbook/assets/image.png)
