### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 雞舍

## 步驟 1
代理(Agent)需要放置**2**層**9**個鐵柵欄方塊。共有**4**個面需要放置**鐵柵欄**。別忘了使用``||agent:Agent 移動 向上||``來建造第二層。

#### ~ tutorialhint
最終你將會有**3**個``||loops:重複||``命令嵌套在一起。確保代理的物品槽中有超過64個方塊！

```ghost
player.onChat("chicken", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 1, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
```
