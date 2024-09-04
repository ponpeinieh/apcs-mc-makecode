### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 巨大的裂縫！

## 步驟 1
程式設計代理人**建造一座橋**橫跨冰中的裂縫。使用 ``||agent:Agent 將物品槽 [1] 設爲使用中||`` 以確保代理人擁有必要的材料。選擇 **橡木** 作為建材，並設置 **64** 為 **方塊數量**。當代理人**未**檢測到前方的方塊時，使用 ``||Loops:重複 判斷||`` 程式設計代理人將橡木木板 **向下** 放置並 **向前** 移動以建造橋樑。

```template
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 1, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, DOWN))) {
    	
    }
})
```

```ghost
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
``` 