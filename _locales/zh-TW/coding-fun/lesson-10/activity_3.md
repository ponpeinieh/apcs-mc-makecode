### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 周圍環境

## 步驟 1

你的任務是開採並收集所有的 **鐵**、**金**、**翡翠(綠寶石)** 和 **鑽石** 方塊。完成任務的建議步驟如下：
在 **檢查下方的方塊** 時，如果該方塊不是 **浮冰**，請編程 Agent 尋找、**破壞** 並 **收集** 下列方塊：**鐵**、**金**、**翡翠** 和 **鑽石**。

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

