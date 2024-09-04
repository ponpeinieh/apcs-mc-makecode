### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 到達熔岩

## Step 1
編寫程序讓代理**向前移動**。當代理**檢查**下方的方塊時，如果不是**熔岩**，代理需要**向下移動**。

```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
``` 