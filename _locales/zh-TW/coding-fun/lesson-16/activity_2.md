### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 建造起始房屋！

## 步驟 1
使用提供的範例代碼來放置一排方塊。然後，代理需要重複相同的步驟 **4 次**，接著 ``||Agent:Agent 移動 [上]||``。這樣我們完成了一層的建置。 我們再重複多次。取得 ``||variable:height(高度)||`` 並將其添加到 ``||loops:重複 執行||`` 塊中。這段代碼將幫助您建造 **一** 棟房屋。

### ~ tutorialHint
在遊戲內聊天時，別忘了輸入您的數字，例如 **house 2 5**。

```template    
 player.onChat("house", function (height, size) {
    for (let index = 0; index < size; index++) {
        agent.setItem(STONE, 1, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```

```ghost
player.onChat("build-simple", function (size, height) {
    for (let index = 0; index < height; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < size; index++) {
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



