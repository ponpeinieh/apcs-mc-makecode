### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 周圍環境

## 步驟 1
當代理**檢查下方的方塊**且該方塊**不是浮冰**時，如果代理**偵測到右側的方塊**，它需要**向前移動**。否則，它需要**向右移動**。在同一個迴圈中，如果代理**檢查下方的方塊**並且該方塊是**鵝卵石**或**礫石**，它需要**破壞下方**並**收集所有物品**。


```template
player.onChat("ice", function () {
    while (0 == 0) {
        if (true) {
        	
        } else {
        	
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE ||agent.inspect(AgentInspection.Block, DOWN) == GRAVEL ) {
        	
        }
    }
})
```
```ghost
player.onChat("2", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE || agent.inspect(AgentInspection.Block, DOWN) == GRAVEL) {
            agent.destroy(DOWN)
            agent.collectAll()
        }
    }
})
```
