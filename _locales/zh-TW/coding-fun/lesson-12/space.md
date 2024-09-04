### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1


# 協作活動

## 步驟 1
選擇你在太空中需要使用的方塊。你會找到我們在課程中使用過的所有方塊供你使用！

```ghost
player.onChat("run", function () {
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
    agent.place(FORWARD)
    agent.destroy(FORWARD)
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
    	
    }
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE || agent.inspect(AgentInspection.Block, DOWN) == GOLD_ORE) {
            agent.turn(LEFT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == DIAMOND_ORE || agent.inspect(AgentInspection.Block, DOWN) == EMERALD_ORE) {
            agent.turn(RIGHT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})

``` 

