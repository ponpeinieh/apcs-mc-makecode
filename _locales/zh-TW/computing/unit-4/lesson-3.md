### @explicitHints 1

# 單元 4: 課程 3 - 編寫動物園獸欄

## 步驟 1
這個課程我們將使用新的方式，**建造器(Builder)**，來建構世界。

將 ``||player:玩家 在聊天指令為||`` 代碼方塊中 **run** 名稱改為 **ocelot_wall**。

從工具箱中點選 ``||Advanced:進階||`` 抽屜，你會看到額外的抽屜顯示出來，選擇打開``||Builder:建造器||`` 抽屜。

``||Builder:建造器||`` 允許玩家使用和操控麥塊的位置機制。可以把 ``||Builder:建造器||`` 想像成一個看不見的 ``||Agent:代理||``。

首先我們告訴**建造器**從哪裡開始。將一個 ``||Builder:建造器 傳送到 相對[~0] [~0] [~0]||`` 代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(pos(0, 0, 0))
})
```

## 步驟 2
將 ``||positions:世界 [0] [0] [0]||`` 座標代碼方塊拖放到你的編碼工作區，取代其中的 ``||positions:相對[~0] [~0] [~0]||`` 座標代碼方塊。

現在將 ``||positions:世界 [0] [0] [0]||`` 座標設置為你想要開始構建牆壁的位置。我們用 **黃色羊毛** 方塊標記了我們打算的起始點，這個位置的座標是 **-38, 69, -576** 。你可以使用不一樣的座標。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
})
```

## 步驟 3
接著告訴**建造器**面向的方位。我們需要告訴它從哪個方向上進行構建。麥塊的世界有從北到南和從東到西，以及上下的網格。最簡單的方法是使用**指南針**來判斷方位。你可以在你的物品欄中找到指南針。

當玩家移動時，**指南針** 也會跟著轉動。你可以用它來找到你的北邊的方向（紅色刻度指向北邊）。我們從指南針得知**建造器**要從**西方**開始建造。

## 步驟 4
返回 ``||Builder:建造器||`` 抽屜，找到 ``||Builder:建造器 面向 [西 (West)||`` 代碼方塊。將其添加到你的代碼中，並使用下拉選單設置構建的方向。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
})
```

## 步驟 5
現在返回 ``||Builder:建造器||`` 抽屜，將一個 ``||Builder:建造器 移動 方向 [前(forward)]||`` 代碼方塊拖放到你的代碼中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 1)
})
```

## 步驟 6
將 ``||Builder:建造器 移動 方向 [前(forward)]||`` 的格數改為你想要構建的方塊數量。在我們的例子中，格數爲**21**。
接著將一個 ``||Builder:建造器 轉動 方向 [左(left)]||`` 代碼方塊拖放到你的代碼中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(LEFT_TURN)
})
```

## 步驟 7
將其更改為你希望 ``||Builder:建造器||`` 下一個面對的方向。在我們的例子中，這將是**右**邊。

添加另一個 ``||Builder:建造器 移動 方向 [前(forward)]||`` 代碼方塊，並將格數改為在這個新方向上你想要構建的總方塊數。在我們的例子中，格數爲**9**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
})
```

## 步驟 8
最後告訴**建造器**建構時所使用的材料方塊。回到 ``||Builder:建造器||`` 抽屜，將一個 ``||Builder:建造器 追蹤路徑 使用||`` 代碼方塊拖放到你的主代碼中。

這告訴你的**建造器**，在移動過程中，留下一條所設定的材料方塊的軌跡。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(GRASS)
})
```

## 步驟 9
使用下拉選單將材料方塊更改為你希望周邊牆壁的材料。在我們的例子中，我們將使用 **石磚**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(STONE_BRICKS)
})
```

## 步驟 10
執行代碼以構建牆壁。``||Builder:建造器||`` 現在應該從位置 **-38, 69, -576** 開始向西移動 **21** 個方塊，右轉並移動 **9** 個方塊，同時在路上放置 **石磚**。建構的結果是一個小圍牆。你會發現這比之前使用的 ``||Agent:代理||`` 和 ``||Blocks:方塊||`` 建構方式快得多。通過一些預先規劃，你可以在幾秒鐘內創建巨大的結構。

## 步驟 11
添加柵欄和其他細節。這個牆壁的目的是不讓豹猫逃走，所以下一步我們可以在上方添加柵欄，以確保它們不會逃走。

## 步驟 12
複製上述編碼，然後調整一下現有代碼，即可完成這一步。我們只需要將**建造器**開始的位置，改為高一個方塊位置(**Y**座標加1)，並將材料更改為 **橡木柵欄**。看看我們的代碼範例.

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-38, 69, -576))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
})
```

## 步驟 13
現在我們可以為**豹猫**圍欄添加一些特色。

## 步驟 14
增加一個新的 ``||player:玩家 在聊天指令為||`` 代碼方塊並命名為 **ocelot**。

## 步驟 15
從 ``||Mobs:生物||`` 抽屜中將一個 ``||Mobs:生物 生成 [動物] 於||`` 代碼方塊拖放到你的新 ``||player:玩家 在聊天指令為||`` 代碼中。

使用下拉選單將 **動物** 元素更改為 **豹貓**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, pos(0, 0, 0))
})
```

## 步驟 16
前往 ``||positions:座標||`` 抽屜，抓取一個 ``||positions:世界 [0] [0] [0]||`` 座標代碼方塊，來取代``||positions:相對 ~[0] ~[0] ~[0]||``座標代碼方塊。然後將座標數字更改為圍欄内的某個位置。在我們的例子中，我們將其設置為 **-50, 69, -580**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, world(-50, 69, -580))
})
```

## 步驟 17
運行你的代碼。完成後，你應該能看到一只 **豹猫** 出現！

## 步驟 18
添加其他獸欄和動物。現在你可以添加更多的獸欄和動物，如 **狼** 和 **北極熊**。考慮它們的棲息地並相應地裝飾它們的獸欄。