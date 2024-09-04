### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 環境

## Step 1
當代理**檢測到下方有方塊**時，代理需要向前移動。如果代理**檢查到下方有方塊**並發現**空氣**，則使用``||player: 玩家 説出||`` 命令說**發現坑洞！**。

```template
player.onChat("crater", function () {
    player.say("發現坑洞！")
})
```
```ghost
player.onChat("crater", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("發現坑洞！")
    }
})
``` 