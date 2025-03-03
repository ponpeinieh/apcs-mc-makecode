### @explicitHints 1

# 活動：代理樹木砍伐者

## 第一步  
將現有的 ``||Player:玩家 在聊天指令為||`` 方塊重命名為 **"tp"**。  
將 ``||Agent:Agent 傳送到玩家||`` 方塊放入 ``||Player:玩家 在聊天指令為 "tp"||`` 方塊內。

## 第二步  
現在，讓我們創建一個方向指令，以便我們可以讓 Agent 轉身。你可以右鍵點擊 ``||Player:玩家 在聊天指令為 "tp"||`` 並選擇 **複製** 來創建一個副本。

將副本重命名為 **"lt"**。

## 第三步  
刪除這個新副本中的內部方塊，並將 ``||Agent:Agent 傳送到玩家||`` 替換為 ``||Agent:Agent 轉動 '左'||``。

### ~ tutorialhint
```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
```

## 第四步  
創建高度變數。將一個 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到編碼工作區，並將其重命名為 **"chop"**。

你將使用一個變數來記錄樹的高度。在 ``||Variables:變數||`` 工具箱抽屜中，點擊 **創建變數** 按鈕。將新變數命名為 **height**。

## 第五步  
將 **height** 初始化為 **0**。將 ``||Variables:變數 設為||`` 方塊拖曳到 ``||Player:玩家 在聊天指令為 "chop"||`` 方塊內。

## 第六步  
在 ``||Variables:變數 設為||`` 方塊中，使用下拉選單選擇 **height** 作為變數，並將 **height** 設為 **0**。

### ~ tutorialhint
```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
})
```

## 第七步  
從樹的底部開始。假設在執行 **chop** 指令時，Agent 已經面向樹的底部。使用 **"tp"** 和 **"lt"** 指令將你的 Agent 放置到位，然後最後執行 **"chop"**。使用一個 ``||Loops:重複 判斷||`` 迴圈，這類似於結合了條件判斷的 ``||Loops:重複||`` 迴圈。只要 Agent 前方有方塊，代碼就會繼續執行。如果 Agent 前方有方塊，它將繼續向上移動。

## 第八步  
將一個 ``||Loops:重複 判斷||`` 迴圈拖曳到 ``||Variables:變數 height 設為||`` 方塊下方。這應該放在 ``||Player:玩家 在聊天指令為 "chop"||`` 方塊內。

## 第九步  
將 ``||Agent:Agent 偵測 方塊 前||`` 方塊拖曳到 ``||Loops:重複 判斷||`` 迴圈中，替換 ``||Logic:成立||``。

### ~ tutorialhint
```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {

    }
})
```

## 第十步  
向上移動並砍伐樹木。將一個 ``||Variables:變數 改變||`` 方塊放入 ``||Loops:重複 判斷||`` 迴圈內。

這個新方塊應該顯示為 ``||Variables:變數 height 改變 1||``。這將使 **height** 變數每次增加 1，這樣我們就可以記錄樹的高度。

## 第十一步  
如果 Agent 頭頂上有樹葉或樹枝，你需要摧毀它們以便讓 Agent 向上移動。將一個 ``||Agent:Agent 破壞||`` 方塊放在 ``||Variables:變數 height 改變 1||`` 方塊下方。你需要從下拉選單中選擇 **上** 作為方向來調整這個方塊。

## 第十二步  
最後，讓你的 Agent 向上移動。抓取一個 ``||Agent:Agent 移動||`` 方塊，然後像上一步一樣從下拉選單中選擇 **上** 作為 **方向**。

### ~ tutorialhint
```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
})
```

## 第十三步  
返回地面。將一個 ``||Loops:重複||`` 迴圈拖曳到 ``||Loops:重複 判斷||`` 迴圈之後，放在 ``||Player:玩家 在聊天指令為 "chop"||`` 方塊內。

## 第十四步  
將 **height** 拖曳到 ``||Loops:重複||`` 迴圈中，替換 **4**。

### ~ tutorialhint
```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
    for (let i = 0; i < height; i++) {

    }
})
```

## 第十五步  
在下降時砍伐樹木。此時，Agent 應該站在樹頂。你需要讓它爬下來，砍伐樹木並收集木材。將一個 ``||Agent:Agent 移動||`` 和 ``||Agent:Agent 破壞||`` 方塊放入 ``||Loops:重複||`` 迴圈內。

## 第十六步  
現在你需要根據情況調整這些方塊。Agent 需要 **向下移動**，並砍伐 **前方** 的每一塊樹木。在 ``||Agent:Agent 移動||`` 方塊中，選擇 **下** 作為方向。Agent 將向下移動。然後，Agent 應該摧毀前方的樹木方塊。``||Agent:Agent 破壞||`` 的預設設置即可。

## 第十七步  
最後，你希望 Agent 收集所有砍伐的木材。將一個 ``||Agent:Agent 收集全部||`` 方塊放在 ``||Loops:重複||`` 迴圈之後。這是我們 ``||Player:玩家 在聊天指令為 "chop"||`` 中的最後一個方塊。

### ~ tutorialhint
```blocks
let height = 0
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("lt", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("chop", function () {
    height = 0
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        height += 1
        agent.destroy(UP)
        agent.move(UP, 1)
    }
    for (let i = 0; i < height; i++) {
        agent.move(DOWN, 1)
        agent.destroy(FORWARD)
    }
    agent.collectAll()
})
```
 