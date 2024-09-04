### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 追踪探測車

## 步驟 1
修正這段代碼。目標如下：當**檢查前方**的方塊**不是**石英時，代理需要**向前移動**。如果檢測到**下方**是金塊，代理需要**向右轉**。如果檢測到**下方**是鐵塊，代理需要**向左轉**。最後，代理需要說，“找到探測車了！”


```template
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, UP) == GOLD_BLOCK) {
            agent.turn(LEFT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("找到探測車了！")
})
```

