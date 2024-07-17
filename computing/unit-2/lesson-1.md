### @explicitHints 1

# Unit2 : Lesson 1 - Code a Road Network

```blocks
player.onChat("run", function () {})
blocks.fill(GRASS, world(0, 0, 0), world(0, 0, 0),FillOperation.Replace)
agent.teleportToPlayer()
agent.move(FORWARD, 1)
agent.turn(LEFT_TURN)
agent.destroy(FORWARD)
agent.place(FORWARD)
agent.collectAll()
```

## Step 1
Rename the **run** element of the ``||player:on chat command||`` block to **road_1**. Select the ``||blocks: fill with||`` code block and drag it into your ``||player:on chat command||`` block.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRASS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 2
Use the drop-down menu to change the type of block from **Grass** to **Gray Concrete**.

### ~ tutorialhint

``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 3
Now open ``||positions:POSITIONS||``  toolbox drawer and drag the ``||positions:world [0] [0] [0]||`` code block onto your coding Workspace.
Drag the ``||positions:world [0] [0] [0]||`` block and replace the ``||positions:relative||`` positions block inside the ``||blocks:fill with||`` block.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 4
Drag another ``||positions:world [0] [0] [0]||`` positions code block from the ``||positions:POSITIONS||`` drawer and replace the second  ``||positions:relative||`` positions block inside the ``||blocks:fill with||`` block.

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 5
We are almost ready to test our code, however there is one more important thing we have to do to make this code work properly. Change the center, or **Y** coordinate, to one number lower. In this example, this will be **68**. Now test your code. If you have coded correctly, you should see a road appear in place of the Grass. 

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -565),
    world(61, 68, -569),
    FillOperation.Replace
    )
})

```

## Step 6
Repeat the steps for the second road.

### ~ tutorialhint
``` blocks
player.onChat("road_2", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -532),
    world(61, 68, -536),
    FillOperation.Replace
    )
})
```

## Step 7
**(Extension)** With two roads done, build more using the code you have just created. When you are finished, go to the **Unit 2 Lesson 1 NPC** and ask for some **carpet** to make road markings with using your agent to place them.
