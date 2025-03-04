### @explicitHints 1

# 活動：金字塔

## 第一步  
以下是金字塔項目的起始代碼。

### ~ tutorialhint
```template
player.onChat("tp", function () {
    player.teleport(positions.create(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(positions.create(-3, 0, -3))
})
player.onChat("pyramid", function (BaseSize) {
    agent.setAssist(AgentAssist.PlaceOnMove, true)
    for (let i = 0; i <= 3; i++) {
        agent.move(SixDirection.Forward, BaseSize - 1)
        agent.turn(TurnDirection.Left)
    }
    agent.move(SixDirection.Up, 1)
    agent.setAssist(AgentAssist.PlaceOnMove, false)
    agent.move(SixDirection.Forward, 1)
    player.runChatCommand("pyramid " + (BaseSize - 2))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
```

## 第二步  
運行代碼，檢查起始代碼的問題。如果你直接運行這個代碼，你會注意到一些奇怪的事情。

## 第三步  
為你的 Agent 裝備一些方塊。

在聊天窗口中輸入 **tp**，將你的 Agent 傳送到你附近。你可能還需要使用 **turn** 指令讓 Agent 轉身，但這可能不是必要的。

## 第四步  
在聊天窗口中輸入 **pyramid 5**，看看會發生什麼。你的 Agent 應該會順利建造金字塔，但它不會停止。Agent 會一直建造下去，無限循環！這是因為在代碼的最後，你有一個不斷調用代碼的方塊。

### ~ tutorialhint
```javascript
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```

## 第五步  
添加 **If 語句**。你的任務是在代碼中添加一些 **If 語句** 來停止無限循環的行為！

### ~ tutorialhint
如果你陷入無限循環，你需要從代碼連接窗口中停止代碼。點擊代碼連接窗口左下角的停止按鈕。

## 第六步  
停止循環。要停止循環，你需要檢查一個變數，然後告訴你的代碼停止循環。在這種情況下，使用 if 語句非常適合。將一個 ``||Logic:如果 那麽 否則||`` 指令拖曳到你的代碼中，使 **if 語句** 包圍 ``||Player:玩家 在聊天指令為 "pyramid"||`` 內的所有代碼。

### ~ tutorialhint
```javascript
player.onChat("pyramid", function (BaseSize) {
    if (true) {
        agent.setAssist(PLACE_ON_MOVE, true)
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 第七步  
現在讓我們輸入條件。你希望當 **大小** 小於 **0** 時停止循環。用戶輸入一個大小，每次通過這段代碼後，大小會減少 **2**。再次強調，這個方塊就是實現這一點的地方。

```javascript
let BaseSize = 0
player.runChatCommand("pyramid " + (BaseSize - 2))
```

## 第八步  
抓取一個 ``||Logic:0 = 0||`` 或 ``||Logic:0 < 0||`` 指令，並將其放入你的 ``||Logic:如果 那麽 否則||`` 中。

### ~ tutorialhint
```javascript
let MadePyramid = false
player.onChat("pyramid", function (BaseSize) {
    // 檢測是否應該繼續建造金字塔
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // 建造金字塔的一層
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 第九步  
你希望你的比較條件顯示為 **'BaseSize > 0'**。如果大小大於零，讓我們建造一些東西；否則，你將向用戶發送一條訊息。

### ~ tutorialhint
```javascript
let MadePyramid = false
player.onChat("pyramid", function (BaseSize) {
    // 檢測是否應該繼續建造金字塔
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // 建造金字塔的一層
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 第十步  
通過這個 If 語句，你停止了循環！你還可以如何改進這段代碼？有兩種情況會使大小為零：當 Agent 剛剛完成建造金字塔時，或者用戶忘記輸入金字塔的大小時。當這種情況發生時，代碼將進入 ``||Logic:如果 那麽||`` 方塊的 else 分支。

## 第十一步  
你能找到一種方法來檢查上述兩種情況（A 和 B）嗎？你將在 else 分支中檢查這一點。在進行挑戰之前，仔細查看我們的最終代碼。這裡有一個提示來解決這個問題。你注意到新的指令了嗎？

### ~ tutorialhint
```javascript
let MadePyramid = false
// 將 Agent 傳送到你附近，但稍微遠一點，
// 這樣當他開始建造時，你有時間離開
player.onChat("tp", function () {
    player.teleport(pos(3, 0, 3))
    agent.teleportToPlayer()
    player.teleport(pos(-3, 0, -3))
})
player.onChat("turn", function () {
    agent.turn(TurnDirection.Left)
})
player.onChat("pyramid", function (BaseSize) {
    // 檢測是否應該繼續建造金字塔
    if (BaseSize > 0) {
        agent.setAssist(PLACE_ON_MOVE, true)
        // 建造金字塔的一層
        for (let i = 0; i <= 3; i++) {
            agent.move(FORWARD, BaseSize - 1)
            agent.turn(TurnDirection.Left)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(FORWARD, 1)
        MadePyramid = true
        player.runChatCommand("pyramid " + (BaseSize - 2))
    } else {

    }
})
```

## 第十二步  
嘗試使用這個變數和一個 ``||Logic:如果||`` 語句來完成挑戰！
