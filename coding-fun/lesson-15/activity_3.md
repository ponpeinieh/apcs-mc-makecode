### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# Pretty things!

## Step 1
Your mission is to construct an alternating pattern of **quartz** and **lapis lazuli** blocks along the floor border of the bath. Start by creating two variables: ``||variable:blockA||`` and ``||variable:blockB||``. Set ``||variable:blockA||`` to a **block of quartz** and ``||variable:blockB||`` to a **lapis lazuli block**. Add these commands to the ``||loops:on start||`` block.

## Step 2
Within the ``||logic:if||`` statement, check if ``||variable:count||`` equals **0**. If true, the Agent needs to place the block from ``||variable:blockA||`` (which should be in its first inventory slot), then ``||agent:destroy down||``, ``||agent:place down||``, and ``||variable:change count by 1||``. Otherwise, the Agent should place the block from ``||variable:blockB||`` (also in the first inventory slot), then place the blocks, and ``||variable:change count by -1||``. After the ``||logic:if else||`` block, have the Agent move **1** block ``||Agent:forward||``.

## Step 3
The Agent needs to repeat the block placement process from Step 2 inside a ``||loops:while||`` loop. The loop should continue as long as the condition ``||Agent:detect block||`` **forward** is false.

## Step 4
The previous steps cover placing blocks along one side of the reservoir. Since the reservoir has **4** sides, add a ``||Loops:repeat [4] times||`` loop block. Inside this loop, reset ``||variable:count||`` to **0** before repeating the logic from the previous steps. After completing each side, use ``||Agent:turn [right]||`` to have the Agent turn and continue building along the next side, moving counterclockwise.


```template
let count = 0
player.onChat("floor", function () {
    count = 0
})
```


```ghost
player.onChat("floor", function () {
    count = 0
    for (let index = 0; index < 4; index++) {
        while (!(agent.detect(AgentDetection.Block, FORWARD))) {
            if (count == 0) {
                agent.setItem(blockA, 1, 1)
                agent.destroy(DOWN)
                agent.place(DOWN)
                count += 1
            } else {
                agent.setItem(blockB, 1, 1)
                agent.destroy(DOWN)
                agent.place(DOWN)
                count += -1
            }
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})
let count = 0
let blockB = 0
let blockA = 0
blockA = BLOCK_OF_QUARTZ
blockB = LAPIS_LAZULI_BLOCK
```
