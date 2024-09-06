### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Chicken Coup

## Step 1
The Agent needs to place **9** blocks of **iron bars** on each of the **4** sides for each layer, and build two layers in total, using ``||agent:agent move up||`` to move to the second layer.

#### ~ tutorialhint
At the end you will have **3** ``||loops:repeat|`` commands nested inside each other. Make sure that the Agent has more than 64 blocks in its inventory!

```ghost
player.onChat("chicken", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 1, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})

``` 
