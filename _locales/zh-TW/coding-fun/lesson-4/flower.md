### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1


# 讓區域更美麗！

## 步驟 1
你需要在藏身處的**4**個邊緣上種植**14**朵蒲公英。代理可以在每一邊種植**14**朵蒲公英。

#### ~ tutorialhint 
不要忘記為``||agent:agent 道具設爲||`` 指令選擇數量。 


```ghost
player.onChat("flower", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 14; index++) {
            agent.setItem(YELLOW_FLOWER, 64, 1)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})
```
