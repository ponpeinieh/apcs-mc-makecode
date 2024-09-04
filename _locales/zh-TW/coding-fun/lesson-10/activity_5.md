### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 全息艙(Holodeck)

## Step 1
利用這個全息艙來提升你的技能！

```ghost
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
agent.place(FORWARD)
agent.destroy(FORWARD)
agent.collectAll()
agent.place(FORWARD)
agent.setItem(GRASS, 1, 1)
})
```
