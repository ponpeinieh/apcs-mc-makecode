### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 定位石頭

## 步驟 1
修正這段代碼。這是代理需要做的事情：**向左移動 4 次**，**摧毀下方**，**向下移動**。如果代理檢測到**石頭**方塊，則需要說「找到石頭了！」，**摧毀前方**並**收集所有**。如果沒有檢測到石頭，代理需要說「這裡沒有石頭！」。每次向下移動後，代理需要**向上移動 1 個方塊**到達表面。這項活動需要重複**4**次。

```template
player.onChat("stone", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(RIGHT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) != STONE) {
            player.say("找到石頭了！")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("這裡沒有石頭！")
        }
        agent.move(UP, 1)
    }
})
```