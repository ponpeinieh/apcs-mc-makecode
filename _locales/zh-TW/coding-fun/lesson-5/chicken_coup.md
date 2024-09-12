### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 雞舍

## 步驟 1
代理需要在每層的**4**個面上放置**9**個**鐵欄杆**方塊，並總共建造**兩層**，使用 ``||agent:Agent 移動 向上||`` 來移動到第二層。

#### ~ tutorialhint
最終你將會有**3**個``||loops:重複 執行||``命令嵌套在一起。確保代理的物品槽中有超過64個方塊！

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
