Here is the translation of the provided text into Traditional Chinese:

### @explicitHints 1

# 單元 2 ：課程 3 - 編碼一排房子

## 建築區 @unplugged
我們將在機構建築前面的建築區建造一座房子。這是一個示例建築。可以是任何設計！

![建築區圖片](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-2/build_area.png)

## 步驟 1
手動建造一座符合您設計規格的房子。請在以黃黑羊毛標記的指定建築區內進行建造。

按左邊的返回箭頭可以再次查看示例和建築區的位置。

## 步驟 2
將 ``||player:玩家 在聊天指令為||`` 區塊中的 **run** 元素重命名為 **clone_here**。將 ``||Blocks:方塊 複製||`` 程式碼區塊拖到 ``||player:玩家 在聊天指令為||`` 中。

這個程式碼區塊允許您克隆麥塊世界中的指定區域並將其放置在其他地方。就像在其他軟體中使用複製和粘貼一樣。您複製一個區域，然後將其粘貼到世界的其他地方。

當您克隆時，建築物的方向或朝向將與複製的建築物相同。所以，如果您複製的建築物面向東，克隆的建築物也將面向東。

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
前兩組座標表示一個三維框，``||Blocks:開始位置||`` 座標作為一個角，``||Blocks:起點||`` 座標作為對角，捕捉之間的所有東西，就像圖片中的框一樣。

``||Blocks:終點||`` 的第三組座標代表您想要粘貼克隆結構的座標。

讓我們試試吧！找到您的模型房子的底角。在提供的圖片中，我們用黃色羊毛標記了這一點。

現在創建一個頂角和對角，用一個隱形的框圍繞結構。我們在提供的圖片中也用**黃色羊毛**做了同樣的事。

## 步驟 4
訪問 ``||positions:坐標||``  工具箱抽屜，並用 ``||positions:世界 [0] [0] [0]||`` 座標替換前兩組座標。我們從**黃色羊毛**中知道這些座標是絕對的。

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
將第一組座標更改為程式碼區塊中的 ``||Blocks:開始位置||`` 座標，將第二組座標更改為下面的 ``||Blocks:起點||`` 座標。請記住，下面的圖片是範例座標。

最後的座標相對於您的玩家，所以您的玩家將成為您想要克隆房子的位置標記。每次想要克隆另一座房子時，您需要移動玩家。

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
測試程式碼。在麥塊中，將玩家移到天空中測試您的程式碼，注意建築克隆的位置。

## 步驟 7
建造您的一排房子。站在您想要在最終建造中放置第一座房子的地方，輸入命令 **clone_here**。您會看到一座房子出現。

完成在城市中創建這一排房子後，您現在可以移除模型房子。