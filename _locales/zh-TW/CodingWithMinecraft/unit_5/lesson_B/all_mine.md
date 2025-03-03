### @explicitHints 1

# 活動：全部都是我的！

## 第一步  
創建 Agent 的控制指令。將現有的 ``||Player:玩家 在聊天指令為||`` 方塊重命名為 **"do"**。

## 第二步  
你可以製作一個簡單的選單來處理所有 Agent 指令。將一個 ``||Logic:如果 那麽 否則||`` 方塊放入 ``||Player:玩家 在聊天指令為 "do"||`` 方塊內。點擊 ``||Logic:如果 那麽 否則||`` 方塊上的 **(+)** 按鈕，添加第三個分支，因為你將測試三個條件。

## 第三步  
點擊 ``||Player:玩家 在聊天指令為 "do"||`` 上的 **(+)** 按鈕，並將 **num1** 重命名為 **AgentOrder**。

### ~ tutorialhint
```blocks
player.onChat("do", function (AgentOrder) {
    if (true) {
        agent.teleportToPlayer()
    } else if (false) {

    } else {

    }
})
```

## 第四步  
現在只需測試用戶輸入的內容。你希望用戶能夠傳送 Agent 並讓它轉身。第三個分支將在用戶未輸入任何內容時提供一些信息。抓取 **‘0 = 0’** 比較方塊並複製它，因為你需要兩個。

將這些方塊放入 ``||Logic:如果 那麽 否則||`` 方塊中。

## 第五步  
調整這些方塊以測試用戶輸入的內容。我們需要測試 ``||Agent:AgentOrder||`` 的值。假設值為 **1** 表示傳送 Agent，值為 **2** 表示讓 Agent 轉身。

### ~ tutorialhint
```blocks
player.onChat("do", function (AgentOrder) {
    if (AgentOrder == 1) {

    } else if (AgentOrder == 2) {

    } else {

    }
})
```

## 第六步  
最後，你只需在分支中添加方塊以使 Agent 執行操作。將一個 ``||Agent:Agent 傳送到玩家||`` 方塊放入 ``||Logic:如果 那麽 否則||`` 的第一個分支中。

## 第七步  
將一個 ``||Agent:Agent 轉動||`` 方塊放入 ``||Logic:如果 那麽 否則||`` 的第二個分支中。

## 第八步  
在最後一個分支中，添加一條訊息以向用戶提供指示。將一個 ``||Player:玩家 説出||`` 方塊放入 ``||Logic:如果 那麽 否則||`` 的第三個分支中。

## 第九步  
將 ``||Player:玩家 説出||`` 中的文字調整為 **輸入 1 傳送或 2 轉身**。

## 第十步  
創建「挖掘」指令。將一個 ``||Player:玩家 在聊天指令為||`` 方塊放入編碼工作區，並將其重命名為 **"dig"**。

## 第十一步  
你只能在生存模式中挖掘鑽石，因此你應該首先確保將遊戲模式更改為生存模式。將 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊放入 ``||Player:玩家 在聊天指令為 "dig"||`` 方塊內。

## 第十二步  
調整 ``||Gameplay:遊戲 更改遊戲模式||``，點擊玩家選擇器的下拉選單，選擇 **自己 @s**。

## 第十三步  
將一個 ``||Logic:如果 那麽 否則||`` 方塊拖曳到 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊之後。

### ~ tutorialhint
```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (true) {
    } else {
    }
})
```

## 第十四步  
尋找鑽石。你希望在 Agent 找到有價值的方塊（如鑽石礦）時發出警報。抓取一個 **等於 (=)** 比較方塊來替換 ``||Logic:如果 那麽 否則||`` 中的 **true**。

## 第十五步  
將一個 ``||Agent:Agent 偵查||`` 方塊拖曳到 **等於 (=)** 比較方塊的第一個欄位中，替換數字 **0**。``||Agent:Agent 偵查||`` 方塊將檢查 Agent 正前方的方塊。

將一個 ``||Blocks:方塊||`` 方塊拖曳到 **等於 (=)** 比較方塊的第二個欄位中。

在 ``||Blocks:方塊||`` 中，使用下拉選單選擇 **鑽石礦** 作為你要檢查的方塊。

### ~ tutorialhint
```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {

    } else {

    }
})
```

## 第十六步  
發財吧！如果你找到 **鑽石礦**，則需要在屏幕上輸出訊息並挖掘礦石。將一個 ``||Player:玩家 説出||`` 方塊拖曳到 ``||Logic:如果 那麽 否則||`` 的第一個分支中。

在 ``||Player:玩家 説出||`` 方塊中，輸入一條訊息，例如 **"我們發財了！"**。

## 第十七步  
將以下三個方塊按順序拖曳到 ``||Player:玩家 説出||`` 方塊下方：``||Agent:Agent 破壞||``、``||Agent:Agent 移動||`` 和 ``||Agent:Agent 收集全部||``。

### ~ tutorialhint
```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
        player.say("我們發財了！")
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.collectAll()
    } else {
    }
})
```

## 第十八步  
摧毀其他方塊並繼續挖掘。如果 Agent 沒有找到鑽石礦，它應該簡單地摧毀前方的非貴重方塊，並向前移動而不收集任何東西。從 ``||Agent:AGENT||`` 中，將 ``||Agent:Agent 破壞||`` 和 ``||Agent:Agent 移動||`` 方塊拖曳到 ``||Logic:否則||`` 分支中。

## 第十九步  
你需要重複這個過程 **64** 次，因此你將使用一個迴圈。將一個 ``||Loops:重複||`` 迴圈拖曳出來，並包圍你的 ``||Logic:如果 那麽 否則||`` 方塊。

在 ``||Loops:重複||`` 迴圈中，輸入數字 **64**。

### ~ tutorialhint
```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    for (let i = 0; i < 64; i++) {
        if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE) {
            player.say("我們發財了！")
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
            agent.collectAll()
        } else {
            agent.destroy(FORWARD)
            agent.move(FORWARD, 1)
        }
    }
})
```

## 第二十步  
讓 Agent 返回。這將讓你的 Agent 向前挖掘 **64** 個方塊，但你需要讓它轉身並返回。因此，你將在 ``||Loops:重複||`` 迴圈外使用另一個迴圈。你正在創建一個「嵌套迴圈」，因為迴圈內還有迴圈。將另一個 ``||Loops:重複||`` 迴圈拖曳出來，並包圍現有的 ``||Loops:重複 64||`` 迴圈。

## 第二十一步  
在 ``||Loops:重複||`` 迴圈中，輸入數字 **2**，因為你希望你的 Agent 挖掘兩行方塊。在第一行結束時，你希望你的 Agent 向上移動並轉身。

## 第二十二步  
將以下四個方塊按順序拖曳到內層 ``||Loops:重複||`` 迴圈下方：``||Agent:Agent 破壞||``、``||Agent:Agent 移動||`` 和兩個 ``||Agent:Agent 轉動||`` 方塊。將它們放在這裡以讓 Agent 返回。你需要使用下拉選單調整其中一些方塊的方向，選擇 **上**。

### ~ tutorialhint
```blocks
player.onChat("dig", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    for (let i = 0; i < 2; i++) {
        for (let i = 0; i < 64; i++) {
            if (agent.inspect(AgentInspection.Block, FORWARD) == DIAMOND_ORE || agent.inspect(AgentInspection.Block, FORWARD) == GOLD_ORE) {
                player.say("我們發財了！")
                agent.destroy(FORWARD)
                agent.move(FORWARD, 1)
                agent.collectAll()
            } else {
                agent.destroy(FORWARD)
                agent.move(FORWARD, 1)
            }
        }
        agent.destroy(UP)
        agent.move(UP, 1)
        agent.turn(TurnDirection.Left)
        agent.turn(TurnDirection.Left)
    }
})
```
