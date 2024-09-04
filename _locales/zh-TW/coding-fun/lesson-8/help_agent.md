### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 鐵礦

## 步驟 1
當代理**檢查下方的方塊**並且這個方塊不是**鐵礦石**時，代理需要**向前移動**。如果代理**檢測到前方有方塊**，則需要**摧毀前方的方塊**。當代理找到鐵礦時，編程讓它**收集**它。注意，為了收集一個方塊，代理需要先摧毀它。

```ghost
player.onChat("4", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    player.say("找到鐵礦石了！")
    agent.destroy(DOWN)
    agent.collectAll()
})
```