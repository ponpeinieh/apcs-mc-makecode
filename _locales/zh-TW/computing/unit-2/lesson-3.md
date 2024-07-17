### @explicitHints 1

# 單元 2 ：課程 3 - 編碼一排房子

## 建築區 @unplugged
我們將在代理機構前面的建築區建造一座房子。圖片是一個示範建築。您可以按照您想要的方式設計！

![建築區圖片](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-2/build_area.png)

## 步驟 1
手動建造一座符合您設計想法的房子。您必須在以黃黑羊毛標記的指定建築區內進行建造。

按左邊的返回箭頭可以再次查看示範建築和建築區的位置。

## 步驟 2
將 ``||player:玩家 在聊天指令為||`` 方塊中的 **run** 名稱重新命名為 **clone_here**。將 ``||Blocks:方塊 複製||`` 程式碼方塊拖到 ``||player:玩家 在聊天指令為||`` 中。
這個程式碼方塊允許您複製麥塊世界中的指定區域，然後放置到其他地方。就像在其他軟體中使用**複製和貼上**一樣。您複製一個區域，然後將其粘貼到世界的其他地方。
當您複製時，所產生的建築物的方向將與被複製的建築物相同。例如，如果被複製的建築物面向東，複製產生的建築物也將面向東。

### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟 3
``||Blocks:方塊 複製||`` 方塊的前兩組座標表示了一個**三維空間的框框**，``||Blocks:開始位置||`` 做為框的一個角，``||Blocks:起點||`` 做為框的另一個角(對角)，這個框框捕捉了這中間的所有東西，就像一個圖片中的框一樣(只是圖片的框框是二維的, 而我們這個框框是三維的)。

``||Blocks:終點||`` 做爲第三組座標，代表您粘貼複製的結構所要放置的地方。

讓我們試試吧！找到您的模型房子的一個底角(例如**右前下方**)。

再找到相對剛剛找到的那個底角斜對面的令一個頂角(**左後上方**)，想像一下我們用一個隱形的框框圍繞了這個範圍的結構。

## 步驟 4
從 ``||positions:坐標||``  工具箱抽屜，拖出兩個``||positions:世界 [0] [0] [0]||`` 座標方塊，替換前兩組座標。

### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    world(0, 0, 0),
    world(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟 5
將第一組世界座標放進到``||Blocks:方塊 複製||``方塊中的 ``||Blocks:開始位置||``。將第二組世界座標放進到``||Blocks:起點||``。請注意，所提示的程式方塊是範例座標, 您的座標可能不相同。

第三組座標是相對坐標, 也就是相對於玩家的位置，所以玩家將成為所複製的房子要放置的位置標記。想要再次複製這座房子時，您僅需要移動玩家到想要複製的位置即可。

### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    world(67, 69, -544),
    world(73, 77, -551),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟 6
測試程式碼。您可以在麥塊中，先將玩家移動到天空中，再測試您的程式碼，注意建築物複製的位置。

## 步驟 7
複製產生一排房子。去到您想要放置的第一座房子的地方，輸入命令 **clone_here**。您會看到一座房子出現。