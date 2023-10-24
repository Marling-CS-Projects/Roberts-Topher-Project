# 2.7 Power up

## Design

### Objectives

set up power ups as well as a win loss system

### Usability Features

### Key Variables

| Variable Name | Use                               |
| ------------- | --------------------------------- |
| biggify       | doubles the players size          |
| smalify       | returns the player back to normal |

### Pseudocode

```

Function big():
    Initialize timer as 0
    Initialize isBig as false
    
    Return an object with the following methods and properties:
    update():
        If isBig is true:
            Set CURRENT_JUMP_FORCE to BIG_JUMP_FORCE
            Decrease timer by the time elapsed since the last frame (dt())
            If timer is less than or equal to 0:
                Call the smallify() method

    isBig():
        Return the value of isBig

    smallify():
        Set the scale of the object to (1, 1)
        Set CURRENT_JUMP_FORCE to JUMP_FORCE
        Reset timer to 0
        Set isBig to false

    biggify(time):
        Set the scale of the object to (2, 2)
        Set timer to the given "time" value
        Set isBig to true



  
  
```

## Development&#x20;

### Outcome

```
function big() {
    let timer = 0
    let isBig = false
    return {
      update() {
        if (isBig) {
          CURRENT_JUMP_FORCE = BIG_JUMP_FORCE
          timer -= dt()
          if (timer <= 0) {
            this.smallify()
          }
        }
      },
      isBig() {
        return isBig
      },
      smallify() {
        this.scale = vec2(1)
        CURRENT_JUMP_FORCE = JUMP_FORCE
        timer = 0
        isBig = false
      },
      biggify(time) {
        this.scale = vec2(2)
        timer = time
        isBig = true     
      }
    }

```

### Challenges

setting a speed value that makes platforming smooth and movement feel responsive

## Testing

Evidence for testing

### Tests

<table data-full-width="true"><thead><tr><th width="136">Test</th><th>Instructions</th><th width="216">What I expect</th><th>What actually happens</th><th>Pass/Fail</th></tr></thead><tbody><tr><td>1</td><td>Interact with star</td><td>the player is twice as large</td><td>As expected</td><td>Pass</td></tr></tbody></table>

### Evidence

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>
