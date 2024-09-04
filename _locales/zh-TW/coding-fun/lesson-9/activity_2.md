### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 深石

## 步驟 1
修正這段代碼。這是代理的目標：向下挖掘至表面，直到在**左側**碰到**金**方塊。在下挖的過程中，代理將檢測是否有**石頭**在它的前方，並收集它。

```template
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, LEFT) == AIR) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
            if (agent.inspect(AgentInspection.Block, FORWARD) != GRASS) {
                player.say("找到石頭了！")
                agent.destroy(FORWARD)
                agent.collectAll()
        }
    }
})
```


