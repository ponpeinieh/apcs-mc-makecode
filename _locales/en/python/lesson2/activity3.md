### @explicitHints true
### @hideIteration true 
# Activity 3 - One step at a time.

```python
blocks.place(GRASS_BLOCK, pos(0, 0, 0))
blocks.block_with_data(GRASS_BLOCK, 0)
```

## Step 1
Write some code to construct a whole staircase, out of **brick blocks** (bricks). You will need to change the **second** and **third** coordinate of the **second** parameter in all of the three `||blocks: place block at position||` commands. You will also need to update the data values in the `||blocks: block with data||` commands. Remember, each data value equals direction with stairs.

### ~ tutorialhint 
Look at the walls to see the east, west, north and south directions.
For data values: 
0 = W  
1 = E   
2 = N  
3 = S
