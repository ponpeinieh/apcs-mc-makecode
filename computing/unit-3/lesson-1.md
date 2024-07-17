### @explicitHints 1

# Unit 3 : Lesson 1 - Code a Park Fence

## Step 1
Rename the **run** element of the ``||Player:on chat command||`` block to **park_fence**. 

Drag and drop the ``||Agent:agent set active slot||`` code block to the coding Workspace and add it to your  ``||Player:on chat command||`` code block.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
})
```
## Step 2
Drag the ``||Loops:repeat [4] times||`` into your ``||Player:on chat command||`` set and change it to **25**.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
    	
    }
})
```

## Step 3
Drag the ``||Agent:agent move [forward]||`` code block to the coding Workspace, add it to your ``||Player:on chat command||`` code block, inside the ``||Loops:repeat [25] times||`` loop, then set it to **1**. 

Drag the ``||Agent:agent place [forward]||`` code block to the coding Workspace, add it to your ``||Player:on chat command||`` code block, inside the ``||Loops:repeats [25] times||`` loop, under the ``||Agent.agent move[forward]||`` code block, then change **forward** to **back**.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
})
```

## Step 4
Drag the ``||Agent:agent turn [left]||`` code block to your ``||PLayer:on chat command||`` code block after the loop. Set it to the direction your Agent needs to turn. In our example, this is **left**. 

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
    agent.turn(LEFT_TURN)
})
```

## Step 5
Test your code. Place your Agent on the starting block and run your code by pressing **T** to open the chat box and type **park_fence**. 

This code will only do one side at a time. Make sure your agent has enough blocks to finish each side before you run! Ask the Unit 3 Lesson 1 NPC for more blocks if you need them.
