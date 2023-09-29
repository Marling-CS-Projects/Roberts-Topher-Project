# 2.6 Cycle 5

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

