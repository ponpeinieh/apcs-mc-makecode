### @explicitHints 1

# Unit 5: Lesson 2 - Animate the Wind Farm

## Step 1
Find a flat area a bit away from your wind farm, where we will build the **blade** models of the turbine, which will be used in the animation.

You can use any material you like for the blades, but the example uses **cyan wool**. However, the **direction** of the blade model you create is very important. This is because we will eventually need to **clone** these blade models onto the wind turbine.

You need to build them according to the direction you want the blades to face in the final animation. In other words, you need to first confirm the orientation of the wind turbine blades (are they facing **south**?).

Remember, when you use the ``||Blocks:clone||`` tool, the direction of the copied items will always remain the same. For example, if a building faces east, it will always face east.

## Step 2
First, we create **three** original models of turbine blades **before carving**.

We can first create one uncarved blade model, then use the clone function to produce the other two.

The uncarved blade is a **7x7** block-sized square wall. We can use the ``||Blocks:fill||`` code block to build it. The main body of the wall is made of **cyan wool**, but a **yellow wool** block is placed in the center as a marker.

#### ~ tutorialhint
``` blocks
player.onChat("wind_blade", function () {
    blocks.fill(
    CYAN_WOOL,
    world(39, 70, -433),
    world(45, 76, -433),
    FillOperation.Replace
    )
    blocks.place(YELLOW_WOOL, world(42, 73, -433))
})
```
 
## Step 3
Next to this uncarved blade model, create two more identical models using the clone method. After we carve these three models into the desired blade shapes, they will become the three frames of the animation. Just like frames in a cartoon or movie, playing them in quick succession creates the illusion of movement.

We can use the ``||Blocks:clone||`` code block to create the other two identical models.

#### ~ tutorialhint
``` blocks
player.onChat("clone_wind_blade", function () {
    blocks.clone(
    world(39, 70, -433),
    world(45, 76, -433),
    world(31, 70, -433),
    CloneMask.Replace,
    CloneMode.Normal
    )
    blocks.clone(
    world(39, 70, -433),
    world(45, 76, -433),
    world(23, 70, -433),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## Step 4
Before carving the blade shapes, let's test if we can successfully clone them to the wind turbine.

We will first process the first blade model, and then repeat these steps for the other two blades.

We know the wind turbine on the hill is facing **south**. You need to first confirm if the center coordinates of the blade are at **(7, 98, -408)**? We can calculate its lower-left corner position, which is **(4, 95, -408)**. This is where we will clone the blade model from the base of the hill.

We can use the ``||Blocks:clone||`` code block to test.

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_1", function () {
    blocks.clone(
    world(39, 70, -433),
    world(45, 76, -433),
    world(4, 95, -408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## Step 5
To test if the second and third blades can also be successfully cloned, we first need to clear the blade copied in the previous step.

#### ~ tutorialhint
``` blocks
player.onChat("remove_blade", function () {
    blocks.fill(
    AIR,
    world(4, 95, -408),
    world(10, 101, -408),
    FillOperation.Replace
    )
})
```

## Step 6
Next, let's test if the second blade can be successfully cloned.

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_2", function () {
    blocks.clone(
    world(31, 70, -433),
    world(37, 76, -433),
    world(4, 95, -408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## Step 7
Similarly, we first clear the blade copied in the previous step, and then test if the third blade can be successfully cloned.

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_3", function () {
    blocks.clone(
    world(23, 70, -433),
    world(29, 76, -433),
    world(4, 95, -408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## Step 8
Now we can carve the walls into the desired blade shapes.

![Building Area Image](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/blades.png)


## Step 9
Finally, we complete the animation.

Choose a new ``||Player:on chat command||`` code block, then change the text to **wind_turbine**. Drag a ``||Loops:Repeat [4] times||`` code block into your ``||Player:on chat command||`` block. Set the number of times to **10**.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 10; index++) {
        
    }
})
```

## Step 10
We will copy the code for the three blade clone tests into the loop from earlier. Test your animation.

#### ~ tutorialhint
``` blocks
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