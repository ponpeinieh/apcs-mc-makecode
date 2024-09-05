### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 建造市政廳！

## 步驟 1
使用 **石頭** 作為建材，創建 **3** 個 ``||variable:變數||``，並命名為 **width(寬度)**、**length(長度)** 和 **height(高度)**；將 ``||variable:變數||`` 設置為正確的參數。別忘了將您的變數添加到 ``||player: 在聊天指令為||`` 命令中。

```ghost
player.onChat("town_hall", function (length, width, height) {
    for (let index = 0; index < height; index++) {
        for (let index = 0; index < 2; index++) {
            for (let index = 0; index < length; index++) {
                agent.setItem(STONE, 1, 1)
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
            for (let index = 0; index < width; index++) {
                agent.setItem(STONE, 1, 1)
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
```
