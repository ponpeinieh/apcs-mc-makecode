
# Unit 5 : Lesson 1 - Code a Wind Farm

## Step 1
Wind turbines make up a wind farm. A ***wind turbine*** is like a windmill, where blades rotate when the wind hits them. In real life as the blades turn, the energy is converted to produce power. Before we start building our wind farm, let's consider a good position for one. In our example, we'll use the hill near our city. Let's use one of the methods we've learned to code a turbine, then clone it to make a farm.  
```template
player.onChat("run", function(){
})
player.teleport(world(19, 79, -413))
```

## Step 2
Test yourself. You should be familiar with the two main coding build methods, ``||Agent:AGENT||`` and ``||Builder:BUILDER||``, now that we have reached the last unit. Decide how you would like to build your turbine using one of these methods. There is an example in the world for you to see just up the hill. 

## Step 3
Use the ``||Blocks:clone||`` command from the ``||Blocks:BLOCKS||`` toolbox drawer to make more of these, if you wish.   


```ghost
player.onChat("run", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
    agent.destroy(FORWARD)
    agent.place(FORWARD)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.teleportToPlayer()
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
        blocks.place(GRASS, world(0, 0, 0))
    }
    while (true) {
    	
    }
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
    builder.place(GRASS)
    builder.mark()
    builder.fill(GRASS)
})
```
