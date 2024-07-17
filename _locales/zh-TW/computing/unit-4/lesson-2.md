### @explicitHints 1

# 單元 4: 第 2 課 - 編寫動物園路徑

## 步驟 1
將 ``||Player:on chat command||`` 程式碼方塊中 **run** 元素改名為 **zoo_path_1**。

選擇 ``||Blocks:fill with||`` 程式碼方塊，並將其拖放到你的 ``||Player:on chat command||`` 方塊中。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟 2
使用下拉菜單將材料類型從 **Grass** 更改為 **Gravel**。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟 3
現在打開左側菜單的 ``||Positions:POSITIONS||``。

請記住，這個抽屜包含通過 **positions** 或 **coordinates** 操控 Minecraft 世界的程式碼方塊。Minecraft 世界中的每個方塊都有 X、Y 和 Z 軸上的位置。

從 ``||Positions:world [0] [0] [0]||`` 拖放兩個橢圓形方塊到你的編碼工作區，並替換 ``||Blocks:from||`` 和 ``||Blocks:to||`` 中的 ``||Positions:[~0] [~0] [~0]||`` 橢圓形方塊。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟 4
現在將來自 **步驟 3** 的第一組座標添加到 ``||Blocks:from||`` 的 ``||Positions:world [0] [0] [0]||`` 中。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟 5
對於 ``||Blocks:to||`` 的 ``||Positions:world [0] [0] [0]||`` 中的第二組座標，添加你在 **步驟 4** 中的座標。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(-60, 69, -575),
    FillOperation.Replace
    )
})
```

## 步驟 6
將中心的 **Y** 座標改為低一號數字。在這個例子中，這將是 **68**。

請記住，座標的中心數字代表高度，從世界底部 **0** 到頂部 **256**。我們必須將其更改為低一個方塊，因為我們想要將我們腳下的草地替換為灰色礫石，而選擇的方塊作為原始座標的一部分是我們的玩家的腿。所以如果我們現在運行代碼，路面將位於地面水平上方一個方塊。這樣，我們就能將草地取代。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 68, -575),
    world(-60, 68, -575),
    FillOperation.Replace
    )
})
```

## 步驟 7
現在測試你的代碼。如果編碼正確，你應該會看到草地被一條道路取代。

## 步驟 8
重複第二、第三和第四個路徑的步驟，使用你的 **Green Wool, Orange Wool** 和 **Red Wool** 標記。如果下面的示例不符合你對動物園路徑網絡的計劃，你可以計劃任何路徑網絡。
 