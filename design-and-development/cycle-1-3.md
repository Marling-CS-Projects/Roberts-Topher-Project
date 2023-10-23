# 2.5 Boss design

## Design

### Objectives



* [x] Do a thing
* [x] Do another thing

### Usability Features

### Key Variables

| Variable Name | Use                                                    |
| ------------- | ------------------------------------------------------ |
| chaseAndFlee  | Sets the constant downward acceleration                |
| onCollide     | Show the anchor point of the Sprite                    |
| Load Sprite   | Used to input what each symbol represents in the level |
| Area          | Collision detection (T/F)                              |
| Body          | Static properties (T/F)                                |
| dir           | Direction of movement                                  |

### Pseudocode

```
Function chaseAndFlee(speed = 60):
    Initialize dir as 1
    Initialize chasing as true
    
    Return an object with the following properties and behaviors:
    id: "chaseAndFlee"
    require: ["pos", "area"]
    add():
        When an object with this behavior is added to the game:
        Set up an event listener for "collide"
        When a collision occurs:
        If the collision is on the left or right side of the object:
        Change the direction of patrol to the opposite direction
    
    update():
        On each game update:
        If chasing is true:
            Calculate the distance between the boss and player
            Get the first player object in the game
            Calculate the distanceToPlayer as the difference in x-position between the boss and the player
            If player exists and the distanceToPlayer is greater than 1000:
                Set dir based on the sign of the distanceToPlayer
                Move the object horizontally by speed multiplied by dir
            Else:
                Set chasing to false
        Else:
            Move the object horizontally by speed multiplied by dir
    
"*" (For all objects with this behavior):
    Create a sprite with the image "Boss"
    Define an area for the object
    Add a physics body to the object
    Add the "chaseAndFlee" behavior to the object
    Set the anchor point of the object to the bottom
    Scale the object by a factor of 3
    Assign the label "Boss" to the object



  
  
```

## Development&#x20;

### Outcome

```
function chaseAndFlee(speed = 60) {
    let dir = 1;
    let chasing = true;

    return {
        id: "chaseAndFlee",
        require: ["pos", "area"],
        add() {
            this.on("collide", (obj, col) => {
                if (col.isLeft() || col.isRight()) {
                    dir = -dir;
                }
            });
        },
        update() {
            if (chasing) {
                // Calculate the distance between boss and player
                const player = get("player")[0];
                var distanceToPlayer = player ? player.pos.x - this.pos.x :Infinity

                // If the player is within a certain range, chase the player
                if (distanceToPlayer > 1000) {
                    dir = Math.sign(distanceToPlayer); // Set direction based on player position
                    this.move(speed * dir, 0);
                } else {
                    chasing = false;
                }
            } else {
                // Flee from the player
                this.move(speed * dir, 0);
            }
        },
    };
}

//

            ],
            "#": () => [
                sprite("Boss"),
                area(),
                body(),
                chaseAndFlee(),
                anchor("bot"),
                scale(3),
                "Boss",
            ],

```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th>What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Get close to boss</td><td>Boss moves towards player</td><td>As expected</td><td>Pass</td></tr><tr><td>2</td><td>Get far from boss</td><td>Boss runs away </td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

