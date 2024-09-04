### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 周圍環境

## 步驟 1
當代理**檢查下方的方塊**且該方塊**不是浮冰**時，將代理程式設置為定位、**破壞**並**收集**以下方塊：**鐵**、**金**、**翡翠方塊(綠寶石)**和**鑽石**。

```ghost
player.onChat("3", function () {
    agent.setItem(STONE, 64, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON || agent.inspect(AgentInspection.Block, DOWN) == GOLD) {
            agent.turn(LEFT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == DIAMOND || agent.inspect(AgentInspection.Block, DOWN) == EMERALD) {
            agent.turn(RIGHT_TURN)
            agent.destroy(DOWN)
            agent.collectAll()
        }
        agent.move(FORWARD, 1)
    }
})
```

