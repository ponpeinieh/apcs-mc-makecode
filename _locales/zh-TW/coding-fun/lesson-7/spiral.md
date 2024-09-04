### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 螺旋

## Step 1
當代理在**檢查前方方塊**且該方塊**不是**金塊時，代理需要**向前移動**。如果代理**未**檢測到前方有方塊，則代理也需要向前移動，否則需要**左轉**。當代理到達**金塊**時，需要**破壞**並**收集**它。

```ghost
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
``` 