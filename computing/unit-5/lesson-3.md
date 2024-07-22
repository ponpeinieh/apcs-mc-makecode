### @explicitHints 1

# Unit 5: Lesson 3 - Coding a Lighting System

## Step 1

We will extend the animation from Lesson 2 by adding the lighting effect produced by the wind turbine. When the turbine blades spin for a period of time, they generate electricity, which lights up the lamps.

First, we need to manually dig a trench and set up the redstone circuit, connecting the redstone lamps.

Directly behind the base of the wind turbine, you need to dig a trench **two blocks deep and five blocks long**. At the last block of the trench, fill in a grass block to create a step up to the surface.

Place **redstone dust** on blocks 2, 3, 4, 5, and 6 (blocks 5 and 6 are on the connected faces of the same block). Do not place redstone dust on block 1 (the block closest to the wind turbine base). This spot is reserved for placing a **redstone block** as the source of the redstone signal. Place a **redstone lamp** on the ground at the end of the trench.

<img src="https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/redstone.png" alt="Redstone Circuit Image" width="200"/>

## Step 2

Before the final loop in Lesson 2, add a ``||Blocks:place [block]||`` code block.

```template
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
})
```

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(GRASS, pos(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
})
```

## Step 3

Use the dropdown menu to change ``||Blocks:grass||`` to ``||Blocks:redstone block||``.

Then, open the ``||positions:Positions||`` drawer and drag the ``||positions:world [0] [0] [0]||`` code block to your programming workspace. Replace the ``||positions:relative||`` position code block in the ``||blocks:fill||`` code block.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
})
```

## Step 4

Go back to Step 1 and get the coordinates of **block 1** (the block closest to the wind turbine base). Fill in these coordinates in the ``||blocks:fill||`` code block with the ``||positions:world [0] [0] [0]||`` code block. In our example, the coordinates are **(7, 81, -412)**.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
})
```

## Step 5

Add another ``||Blocks:place [block]||`` code block after the loop. Note that it should be placed outside the loop.

You can use the copy function to duplicate the code block that placed the redstone block earlier.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
})
```

## Step 6

Use the dropdown menu to change ``||Blocks:redstone block||`` to ``||Blocks:air||``.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
    blocks.place(AIR, world(7, 81, -412))
})
```

## Step 7

Test your code. If successful, your **redstone lamp** should light up every time you run the **wind_turbine** command.

## Step 8

Get the ``||Loops:repeat infinitely||`` code block. This code block creates a loop that runs endlessly, allowing us to keep the animation running continuously.

## Step 9

Drag the ``||Loops:repeat infinitely||`` block into the coding workspace. Then drag all the code inside the ``||player:on chat command wind_turbine||`` block into the ``||Loops:repeat infinitely||`` block.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
    blocks.place(AIR, world(7, 81, -412))
})
```   

## Step 10

Change the number of repetitions in the ``|||Loops:repeat [10] times||`` block to **20**.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
    blocks.place(AIR, world(7, 81, -412))
})
```      

## Step 11

Simulate wind variations. Finally, we need to add some code to simulate the wind turbine stopping when there is no wind. Currently, our turbine spins endlessly, causing the redstone lamp to turn on and off rapidly. A proper **pause** in this code will create this effect.

## Step 12

Return to the ``||Loops||`` drawer and select the ``||Loops:pause (ms)||`` code block. Drag and drop it into your code, placing it after the last ``||Blocks:place [] at AIR||`` code block. Set the time to **5000**.

5000 milliseconds (ms) will pause our animation for 5 seconds, simulating the wind turbine pausing for 5 seconds.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(7, 81, -412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
            world(39, 70, -433),
            world(45, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(31, 70, -433),
            world(37, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
        blocks.clone(
            world(23, 70, -433),
            world(29, 76, -433),
            world(4, 95, -408),
            CloneMask.Replace,
            CloneMode.Normal
        )
    }
    blocks.place(AIR, world(7, 81, -412))
    loops.pause(5000)
})
```

## Step 13

Run and test your code. Your wind turbine blades should now spin 20 times, stop for 5 seconds, and then repeat in an endless loop. Your **redstone lamp** should only light up when the wind turbine blades are spinning.