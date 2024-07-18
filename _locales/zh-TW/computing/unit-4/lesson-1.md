### @explicitHints 1

# 單元 4: 課程 1 - 編寫動物園入口

## 步驟 1
將 ``||player:玩家 在聊天指令為||`` 代碼方塊中 **run** 名稱改為 **build_gates**。

拖放 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊到你的編碼工作區，並設置數字為 **1**。然後添加一個 ``||agent:Agent 移動 [前]||`` 代碼方塊，將方向設為**上**方，距離設為 **1**。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
})
```

## 步驟 2
將 ``||Loops:重複 [4] 次||`` 代碼方塊拖放到 ``||player:玩家 在聊天指令為||`` 方塊中，並將數字設置為 **15**。這將是一入口兩側柱子的高度。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {

    }
})
```

## 步驟 3

接著我們要建構第一根柱子。

將 ``||Agent:Agent 放置 [前]||`` 代碼方塊拖放到編碼工作區中，將方向設為 **下**。

加入一個 ``||agent:Agent 移動 [前]||`` 代碼方塊，將其方向設為 **右**邊，距離設為 **1**。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
    }
})
```

## 步驟 4
拖放另一個 ``||Agent:Agent 放置 [前]||`` 代碼方塊，將方向設為 **下**。

再次拖放一個 ``||agent:Agent 移動 [前]||`` 代碼方塊到編碼工作區，方向保持為 **前**方，距離為**1**。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## 步驟 5
拖放另一個 ``||Agent:Agent 放置 [前]||`` 代碼方塊，將方向設為 **下**。

然後再拖放一個 ``||agent:Agent 移動 [前]||`` 代碼方塊到編碼工作區，將其方向設為 **左**邊，距離為**1**。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
    }
})
```

## 步驟 6
再拖放另一個 ``||Agent:Agent 放置 [前]||`` 代碼方塊，將方向設為 **下**。

於是我們完成了柱子的第一層的建構。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
    }
})
```

## 步驟 7

現在，我們需將我們的 `||Agent:代理||`` 移動到下一層的起始位置。

拖放兩個 ``||agent:Agent 移動 [前]||`` 代碼方塊到編碼工作區，放在 ``||Agent:Agent 放置 [下]||`` 代碼方塊下方。將第一個代碼方塊的方向設爲**後**方，第二個代碼方塊的方向設為**上**方。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## 步驟 8
將你的代理移動到 **黃色羊毛** 方塊上。

## 步驟 9
執行你的代碼。觀察你的代理建造大門的第一根支柱。

## 步驟 10
重複執行上面的代碼來建造第二根支柱。先將代理定位在另一個 **黃色羊毛** 方塊上，然後再次執行你的代碼。現在你應該有兩個柱子。

## 步驟 11
接著建構一個標誌文字入口。我們需要在頂部加入文字標誌。

獲取一個新的 ``||player:玩家 在聊天指令為||`` 代碼方塊，並將名稱 **jump** 改為 **zoo_sign**。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {

})
```

## 步驟 12
取得 ``||Blocks:方塊 輸出 [HELLO]||`` 代碼方塊，並將其拖放到新的 ``||player:玩家 在聊天指令為||`` 代碼方塊中。

將 **HELLO** 字串改為 **ZOO**。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    GRASS,
    pos(0, 0, 0),
    WEST
    )
})
```

## 步驟 13
接著將使用的方塊材料類型從 **草地** 更改為 **橡木**。

拖放一個 ``||positions:世界 [0] [0] [0]||`` 座標代碼方塊，替換掉``||Blocks:方塊 輸出 [ZOO]||`` 代碼方塊中位置的 ``||positions:相對 [~0] [~0] [~0]||`` 代碼方塊。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(0, 0, 0),
    WEST
    )
})
```

## 步驟 14
更改 ``||positions:世界 [0] [0] [0]||`` 座標中的數字，將其設置為你希望文字開始的位置。在我們的代碼範例中，這是 **-31, 83, -560**。在使用這些數字時，請記住負號的重要性。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    WEST
    )
})
```

## 步驟 15
更改 ``||Blocks:方位||`` 的選項，來設定文字顯示的方向。在我們的代碼範例中，這是 **北 (North)**。

你可以在你的世界中多方嘗試一下文字標誌的效果，具體狀況將取決於你選擇創建的文字、放置的地方以及它們的方向。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    NORTH
    )
})
```

## 步驟 16
測試你的代碼。在聊天功能中輸入 **zoo_sign**。你將看到 **ZOO** 這個詞出現在動物園門上空中。
