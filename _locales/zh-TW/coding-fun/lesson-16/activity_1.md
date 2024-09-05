### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 採礦資源！

## 步驟 1
Agent 需要挖掘 **金礦石** 和 **鐵礦石** 方塊。嘗試創建幾個 ``||Player:玩家 在聊天指令為||`` 命令，讓 Agent 向不同方向移動，例如 **Forward(前進)**、**back(後退)**、**right(右轉)**。您可以使用變數來指定 Agent 移動的距離，而不是明確指定移動的步數。在遊戲內聊天時，輸入 **forward** 和 **一個數字**，例如 **forward 5**，如果您希望 Agent **向前移動 5 步**。這樣您可以在不改變代碼的情況下，即時更改 Agent 需要移動的步數。

### ~ tutorialHint
別忘了添加 ``||Agent:Agent 破壞||`` 和 ``||Agent:Agent 收集||`` 塊來編程 Agent 挖掘礦物。

```template
player.onChat("forward", function (num1) {
    agent.move(FORWARD, num1)
})
```
```ghost
player.onChat("right", function (num1) {
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("back", function (num1) {
    agent.turn(RIGHT_TURN)
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("left", function (num1) {
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("collect", function () {
    agent.destroy(DOWN)
    agent.collectAll()
})
```


