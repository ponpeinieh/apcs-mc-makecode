### @explicitHints 1

# 單元 4: 課程 2 - 編寫動物園路徑

## 步驟 1
將 ``||player:玩家 在聊天指令為||`` 代碼方塊中 **run** 名稱改名為 **zoo_path_1**。

選擇 ``||Blocks:方塊 填充||`` 代碼方塊，並將其拖放到你的 ``||player:玩家 在聊天指令為||`` 方塊中。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRASS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟 2
使用下拉選單將方塊材料類型從 **草地** 更改為 **礫石**。

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
現在打開左側工作箱的 ``||positions:座標||``。
這個``||positions:座標||``抽屜包含了操控麥塊世界座標的代碼方塊。麥塊世界中的每個方塊都有 X、Y 和 Z 軸上的位置。
拖放兩個 ``||positions:世界 [0] [0] [0]||`` 座標代碼方塊到你的編碼工作區，並替換 ``||Blocks:起點||`` 和 ``||Blocks:終點||`` 中的 ``||Positions: 相對 [~0] [~0] [~0]||`` 座標代碼方塊。

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
將**黃金方塊**所在的第一組座標 **-40, 69, -575** 設定到 ``||Blocks:起點||`` 的 ``||positions:世界 [0] [0] [0]||`` 中。

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
將第二組座標 **-60, 69, -575** 設定到 ``||Blocks:終點||`` 的 ``||positions:世界 [0] [0] [0]||`` 中。

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
將中間的 **Y** 座標減少1。在這個例子中，這將是 **68**。

請記住，**Y** 座標數字代表高度。我們最初獲取的**Y** 座標是玩家的脚所在的高度。
我們必須將其**Y**座標減少1，這個才是我們腳下的草地的**Y**座標。

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
重複第二、第三和第四個路徑的步驟，使用 **綠色羊毛, 橘色羊毛和紅色羊毛** 標記。你也可以規劃任何其他的路徑。
