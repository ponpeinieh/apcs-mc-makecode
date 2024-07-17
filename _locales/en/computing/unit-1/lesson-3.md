### @hideIteration true 
### @explicitHints true


# Unit 1 : Lesson 3

## Step 1
With everything you have learnt so far, can you code your agent to build a bridge across the water? 
The gap is 3 blocks wide. 
When done, press the **green triangle button** to compile the code, then go to Minecraft, press **T** and type **build_a_bridge**.

### ~ tutorialhint
Don't forget to place **down** when placing blocks!   
Also make sure your Agent has **building material** in its inventory. The blocks should be in **slot 1**.


```ghost
player.onChat("run", function () {
    player.say(":)")
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.place(FORWARD)
    agent.destroy(FORWARD)
    agent.collectAll()
})
``` 