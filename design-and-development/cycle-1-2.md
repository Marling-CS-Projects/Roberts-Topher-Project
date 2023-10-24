# 2.4 Enemy design

## Design

### Objectives

Set up the enemy&#x20;

* [x] code the funtion to make the enemy walk left and right
* [x] And swap direcions when colliding with a wall
* [x] Adding collison so when the player and the enemy colides (on top) the enemy dies

### Usability Features

### Key Variables

| Variable Name | Use                                                    |
| ------------- | ------------------------------------------------------ |
| patrol        | Sets the constant downward acceleration                |
| onCollide     | Show the anchor point of the Sprite                    |
| Load Sprite   | Used to input what each symbol represents in the level |
| Area          | Collision detection (T/F)                              |
| Body          | Static properties (T/F)                                |
| dir           | Direction of movement                                  |

### Pseudocode

```

Function patrol(speed = 60, dir = 1):
    Return an object with the following properties and behaviors:
    id: "patrol"
    require: ["pos", "area"]
    add():
        When an object with this behavior is added to the game:
        Set up an event listener for "collide"
        When a collision occurs:
        If the collision is on the left or right side of the object:
        Change the direction of patrol to the opposite direction

    update():
        On each game update:
        Move the object in the horizontal direction at a speed of "speed" multiplied by "dir"

"*" (For all objects with this behavior):
    Create a sprite with the image "bad guy"
    Define an area for the object
    Add a physics body to the object
    Add the "patrol" behavior to the object
    Set the anchor point of the object to the bottom
    Assign the label "enemy" to the object


  
  
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
        
        
         
    // Handle player collision with enemies
    player.onCollide("enemy", (enemy, col) => {
        if (col.isBottom()) {
            // Kill the enemy when collision is from the top
            destroy(enemy);
        } else {
            // Player collided with the enemy from the side or below, go to the "lose" scene
            go("lose");
        }
    });

                
//
        

```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th>What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Input Left</td><td>Move left</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>Input Right</td><td>Move Right </td><td>As expected</td><td>Pass</td></tr><tr><td>3</td><td>Input space</td><td>Move up </td><td>As expected</td><td>Pass</td></tr><tr><td>4</td><td>Input space (airborne)</td><td>Move up while air born </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

![](<../.gitbook/assets/image (4).png>)

