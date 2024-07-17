### @explicitHints 1

# 單元 4: 第 3 課 - 編寫動物園獸欄

## 步驟 1
告訴建造者從哪裡開始。在 MakeCode 中，將 ``||Player:on chat command||`` 方塊中 **run** 元素改名為 **ocelot_wall**。

訪問屏幕左側的 ``||Advanced:ADVANCED||`` 抽屜，然後訪問屏幕左側的 ``||Builder:BUILDER||`` 抽屜。``||Builder:BUILDER||`` 抽屜允許玩家訪問和操作 Minecraft 的位置機制。想像 ``||Builder:BUILDER||`` 就像一個看不見的 ``||Agent:Agent||``。

將一個 ``||Builder:builder teleport to [~0] [~0] [~0]||`` 方塊拖放到你的 ``||Player:on chat command||`` 方塊中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(pos(0, 0, 0))
})
```

## 步驟 2
將 ``||Positions:world [0] [0] [0]||`` 橢圓形方塊拖放到你的編碼工作區，取代其中已有的 **relative** 座標橢圓形方塊。

現在將 ``||Positions:world [0] [0] [0]||`` 座標設置為你想要開始構建牆壁的位置。我們在座標 **-40, 69, -575** 上用 **Gold Block** 標記了我們打算的起始點。在你的工作簿中寫下你的起始點或第一個標記的座標。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
})
```

## 步驟 3
告訴建造者方向。現在，我們需要告訴它在哪個方向上進行構建。記住，Minecraft 的世界有從北到南和從東到西，以及上下的網格。最簡單的方法是使用指南針。

你可以在你的物品欄找到一個指南針。

當你移動時，**指南針** 也會移動。你可以用它來找到你的北（紅色刻度指向北），東、南和西。指南針上的方向是西。這就是我們希望 ``||Builder:BUILDER||`` 工作的方向。

## 步驟 4
返回 ``||Builder:BUILDER||`` 抽屜，找到 ``||Builder:builder face [West (negative X)||`` 方塊。將其添加到你的主代碼中，並使用下拉菜單設置構建的正確方向。

註：如果玩家朝東、北或南，請相應地更改此代碼方塊。總結一下，你使用 **指南針** 找到希望 ``||Builder:BUILDER||`` 前進的方向，然後將其輸入到此代碼方塊中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
})
```

## 步驟 5
現在返回 ``||Builder:BUILDER||`` 菜單，將一個 ``||Builder:builder move [forward]||`` 方塊拖放到你的主代碼中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 1)
})
```

## 步驟 6
將 ``||Builder:builder move [forward]||`` 的數字更改為你想要構建的方塊數量。在我們的例子中，這是 **21**，但你的獸欄可能不同。現在將一個 ``||Builder:builder turn [left]||`` 方塊拖放到你的主代碼中。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(LEFT_TURN)
})
```

## 步驟 7
將其更改為你希望 ``||Builder:BUILDER||`` 下一個面對的方向。在我們的例子中，這將是右邊。添加另一個 ``||Builder:builder move [forward]||`` 方塊，並將數字更改為這個新方向上你想要構建的總方塊數。在我們的例子中，這是 **9**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
})
```

## 步驟 8
告訴建造者要使用的材料。最後，給你的 ``||Builder:BUILDER||`` 一些建造物件。返回 ``||Builder:BUILDER||`` 抽屜，將一個 ``||Builder:builder trace a path from mark with||`` 方塊拖放到你的主代碼中。

這告訴你的建造者在移動時在其過程中留下一條給定材料的軌跡。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(GRASS)
})
```

## 步驟 9豹猫
使用下拉菜單將材料元素更改為你希望周邊牆壁的材料。在我們的例子中，我們將使用 **石磚**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(STONE_BRICKS)
})
```

## 步驟 10
運行代碼以構建牆壁。測試你的代碼。``||Builder:BUILDER||`` 現在應該從位置 **-40, 69, -575** 開始向西移動 **21** 個方塊，左轉並移動 **9** 個方塊，同時在路上放置 **石磚**。結果是一個圍繞你的豹猫圍欄的小圍牆。你會發現這比之前的 ``||Agent:Agent||`` 和 ``||Blocks:BLOCKS||`` 課程快得多。通過一些預先規劃，你可以在幾秒鐘內創建巨大的結構。

## 步驟 11
添加柵欄和其他細節。這個牆壁不能讓豹猫逃走，讓我們在上方添加柵欄，以確保它們不會逃走。

## 步驟 12
重複上述編碼或調整你現有的代碼來完成這一步。你只需要將位置更改為高一個方塊並將材料更改為 **橡木柵欄**。看看我們的例子：

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
})
```

## 步驟 13
現在我們可以為豹猫圍欄添加一些特色。

## 步驟 14
在編碼窗口中添加一個新的 ``||Player:on chat command||`` 方塊並命名為 **ocelot**。

## 步驟 15
從 ``||Mobs:MOBS||`` 菜單中將一個 ``||Mobs:spawn [animal] at||`` 方塊拖放到你的新 ``||Player:on chat command||`` 代碼中。

使用下拉菜單將 **animal** 元素更改為 **ocelot**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, pos(0, 0, 0))
})
```

## 步驟 16
前往 ``||Positions:POSITIONS||`` 抽屜，抓取一個 ``||Positions:world [0] [0] [0]||`` 來取代 **relative** 座標橢圓形。然後將數字更改為圍欄內的位置。在我們的例子中，我們將其設置為 **-50, 69, -580**。

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, world(-50, 69, -580))
})
```

## 步驟 17
生成豹猫。運行你的代碼。完成後，你應該能看到一只 **豹猫** 出現！

## 步驟 18
添加其他獸欄和動物。現在你可以添加更多的獸欄和動物，如 **狼** 和 **北極熊**。考慮它們的棲息地並相應地裝飾它們的獸欄。