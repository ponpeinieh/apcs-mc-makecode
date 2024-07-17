### @explicitHints 1

# 單元 4: 第 1 課 - 編寫動物園入口

## 步驟 1
將 ``||Player:on chat command||`` 程式碼方塊中 **run** 元素改名為 **build_gates**。

拖放 ``||Agent:agent set active slot||`` 程式碼方塊到你的編碼工作區，並設置數字為 **1**。然後添加一個 ``||Agent:agent move [forward]||`` 程式碼方塊，使用下拉菜單將其設置為 **up**，數字設置為 **1**。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
})
```

## 步驟 2
將 ``||Loops:repeat [4] times||`` 程式碼方塊拖放到你的 ``||Player:on chat command||`` 方塊中，並將數字設置為 **15**。這將是一個大門。

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
將 ``||Agent:agent place [forward]||`` 程式碼方塊拖放到編碼工作區中，使用下拉菜單將其設置為 **down**。

在你的主要代碼中添加一個 ``||Agent:agent move [forward]||`` 程式碼方塊，使用下拉菜單將其設置為 **right**，數字設置為 **1**。

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
從 ``||Agent:Agent||`` 抽屜中拖放另一個 ``||Agent:agent place [forward]||`` 程式碼方塊，將其設置為 **down**。

再次從 ``||Agent:Agent||`` 抽屜中拖放一個 ``||Agent:agent move [forward]||`` 程式碼方塊到編碼工作區，保持設置為 **forward** 和 **1**。

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
從 ``||Agent:Agent||`` 抽屜中拖放另一個 ``||Agent:agent place [forward]||`` 程式碼方塊，將其設置為 **down**。

然後再從 ``||Agent:Agent||`` 抽屜中拖放一個 ``||Agent:agent move [forward]||`` 程式碼方塊到編碼工作區，將其設置為 **left**，數字設置為 **1**。

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
從 ``||Agent:Agent||`` 抽屜中拖放另一個 ``||Agent:agent place [forward]||`` 程式碼方塊，將其設置為 **down**。

現在，我們只需將我們的 ``||Agent:Agent||`` 移動到下一個起始位置，以完成門的這部分代碼。

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
返回 ``||Agent:Agent||`` 抽屜，拖放兩個 ``||Agent:agent move [forward]||`` 程式碼方塊到編碼工作區，並連接到 ``||Agent:agent place [down]||`` 方塊下方。使用下拉菜單在第一個方塊中將 **forward** 改為 **back**，在第二個方塊中將 **forward** 改為 **up**。

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
使用哨子將你的代理定位在 **黃羊毛** 方塊上。

## 步驟 9
運行你的代碼。在聊天功能中輸入你的 ``||Player:on chat command||``，然後觀察你的代理建造門的第一支柱。

## 步驟 10
重複這個步驟來建造第二支柱。使用哨子將你的代理定位在另一個 **黃羊毛** 方塊上，然後再次運行你的代碼。現在你應該有兩個木柱。

## 步驟 11
編寫標誌入口。現在我們需要在頂部添加標誌。

獲取一個新的 ``||Player:on chat command||`` 方塊，並將 **jump** 元素改名為 **zoo_sign**。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {

})
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

## 步驟 12
選擇 ``||Blocks:print [HELLO]||`` 程式碼方塊，並將其拖放到你的新的 on chat command 代碼方塊中。

將 **HELLO** 文本更改為 **ZOO**。

#### ~ tutorialhint
``` blocks
player.on

Chat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(0, 0, 0),
    WEST
    )
})
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

## 步驟 13
使用下拉菜單將方塊材料類型從 **Grass** 更改為 **Oak Wood**。

拖放一個 ``||Positions:world [0] [0] [0]||`` 橢圓形方塊，替換你的 ``||Blocks:[~0] [~0] [~0]||`` 橢圓形方塊，放入你的 ``||Blocks:print [ZOO]||`` 方塊中。

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

## 步驟 14
更改 ``||Positions:world||`` 位置中的座標，將其設置為你希望文字開始的位置。在我們的示例中，這是 **-31, 83, -560**。在使用這些數字時，請記住負號的重要性。

這可能需要在你的世界中進行一些試驗和錯誤，具體取決於你選擇創建多少字母、它們放置在哪裡以及它們的方向如何。
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

## 步驟 15
更改 ``||Blocks:along||`` 的值，以適應你希望文字走的方向。在我們的示例中，這是 **North (negative Z)**，但在你自己的版本中，可能會有所不同。

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

## 步驟 16
運行代碼。測試你的代碼。在聊天功能中輸入 **zoo_sign** 命令，然後按 Enter 鍵。你將看到 **ZOO** 這個詞出現在動物園門上空中。
