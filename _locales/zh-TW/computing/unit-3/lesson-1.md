### @explicitHints 1

# 單元 3：課程 1 - 編碼公園圍欄

## 步驟 1
將 ``||Player:on chat command||`` 塊中的 **run** 元素重新命名為 **park_fence**。

將 ``||Agent:agent set active slot||`` 代碼塊拖放到編碼工作區並添加到你的 ``||Player:on chat command||`` 代碼塊中。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
})
```
## 步驟 2
將 ``||Loops:repeat [4] times||`` 拖放到你的 ``||Player:on chat command||`` 中並更改為 **25**。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
    	
    }
})
```

## 步驟 3
將 ``||Agent:agent move [forward]||`` 代碼塊拖放到編碼工作區中，添加到你的 ``||Player:on chat command||`` 代碼塊中，在 ``||Loops:repeat [25] times||`` 循環內部，然後設置為 **1**。

將 ``||Agent:agent place [forward]||`` 代碼塊拖放到編碼工作區中，添加到你的 ``||Player:on chat command||`` 代碼塊中，在 ``||Loops:repeats [25] times||`` 循環中，在 ``||Agent.agent move[forward]||`` 代碼塊下方，然後將 **forward** 更改為 **back**。

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
在循環後，將 ``||Agent:agent turn [left]||`` 代碼塊拖放到你的 ``||PLayer:on chat command||`` 代碼塊中。設置它為你的代理需要轉向的方向。在我們的例子中，這是 **left**。

###  ~ tutorialhint
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
測試你的代碼。將你的代理放在起始塊上，按 **T** 打開聊天框並輸入 **park_fence** 來運行你的代碼。

此代碼每次只做一邊。確保你的代理在運行之前有足夠的方塊完成每一邊！如果需要，向單元 3 課程 1 NPC 索要更多方塊。
```
```

