### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 分隔的家庭！

## 步驟 1
程式設置代理在冰上的裂縫處建立一座橋。確保代理的庫存中有 **64** 個 **橡木木板**。

#### ~ tutorialhint 
不要忘記在 **while** 迴圈中使用 **not**。考慮一下你希望代理放置方塊的位置。

```ghost
player.onChat("family", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
})
```