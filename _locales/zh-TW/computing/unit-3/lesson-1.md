### @explicitHints 1

# 單元 3：課程 1 - 編碼公園圍欄

## 步驟 1
將 ``||player:玩家 在聊天指令為||`` 代碼方塊中的 **run** 名稱重新命名為 **park_fence**。

將 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊拖放到編碼工作區，並添加到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
})
```
## 步驟 2
將 ``||Loops:重複 [4] 次||``代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||``代碼方塊中，並將次數改為 **25**。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
    	
    }
})
```

## 步驟 3
將 ``||agent:Agent 移動 [前]||`` 代碼方塊拖放到編碼工作區中，添加到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，在 ``||Loops:重複 [25] 次||`` 迴圈內部，然後距離設為 **1**。

將 ``||Agent:Agent 放置 [前]||`` 代碼方塊拖放到編碼工作區中，添加到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，在 ``||Loops:重複 [25] 次||`` 迴圈中，在 ``||agent:Agent 移動 [前]||`` 代碼方塊下方，然後將**前**方改為**後**方。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
})
```

## 步驟 4
在迴圈後，將 ``||agent:Agent 轉動 [左]||`` 代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中。設置你的代理需要轉的方向。在我們的例子中，方向是**左**邊。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
    agent.turn(LEFT_TURN)
})
```

## 步驟 5
測試你的代碼。將你的代理放在起始位置方塊上，按 **T** 打開聊天框並輸入 **park_fence** 來運行你的代碼。

此代碼每次只建構一邊的柵欄。確保你的代理在運行之前有足夠的柵欄方塊完成每一邊！如果需要，向**單元 3 課程 1 NPC** 索取更多的方塊。
