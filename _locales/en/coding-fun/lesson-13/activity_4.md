### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# Change the world!

## Step 1
Use the ``||player:on player walk||`` event to place a block at the specified ``||positions:world||`` coordinates (**100, 68, 100**). Create a ``||variable||`` named **count**, which will serve as the block ID. Then, add the ``||change count by 1||`` block and the ``||blocks:place||`` block, using **count** as the block ID. Each time **count** increases by 1, the corresponding block is placed: for example, count = 1 places Stone, count = 2 places Grass, count = 3 places Dirt, and so on.

To reset the block ID, use another event, such as ``||player:on player fall||``. In this event, drag the ``||set count||`` block and set **count** to 0. Then, use the ``||blocks:place||`` block again with the ``||variable:count||`` as the block ID at the same coordinates. This way, every time you jump in the world, the block will reset to its initial state.

### ~ tutorialhint 
Don't forget to use ``||positions: world||`` positions to indicate the coordinates. 

```blocks
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
```


```ghost
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
player.onTravelled(FALL, function () {
    count = 0
    blocks.place(count, world(100, 68, 100))
})
```

