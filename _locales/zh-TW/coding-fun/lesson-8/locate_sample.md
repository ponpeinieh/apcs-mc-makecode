### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 定位樣本！

## 步驟 1
**當**代理**檢查下方的方塊**且**沒有**找到**藍色冰塊**時，編程讓代理**摧毀**並**向下移動**。當代理找到**藍色冰塊**時，需**摧毀下方**並**收集**樣本。

```ghost 
player.onChat("ice", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
    
})
```