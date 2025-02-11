### @explicitHints 1

# 活動：製作指南針玫瑰

## 第一步  
創建一個新的 ``||Player:玩家 在聊天指令為||`` 指令。將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳出來，並將指令更改為 **"compassrose"**。

### ~ tutorialhint
```blocks
player.onChat("compassrose", function () {
})
```

## 第二步  
接著，將 ``||Blocks:方塊 填充||`` 方塊放入 ``||Player:玩家 在聊天指令為||`` 方塊內。  
將 ``||Blocks:方塊 填充||`` 方塊中的 **草地** 更改為你想要的軸線材質。我們的範例使用 **灰色羊毛** 作為軸線。

## 第三步  
在 **起點** 輸入 **(~-10 ~-1 ~0)**，並在 **終點** 輸入 **(~10 ~-1 ~0)**。這將沿著 X 軸生成一條 21 個方塊的線。這條線會在你的腳下，而你會位於正中心。

### ~ tutorialhint
```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    GRAY_WOOL,
    pos(-10, -1, 0),
    pos(10, -1, 0),
    FillOperation.Replace
    )
})
```

## 第四步  
印出東和西的方向。找到 ``||Blocks:方塊 輸出||`` 方塊。這個方塊可以用任何你選擇的方塊沿指定軸印出文字。

## 第五步  
拖出兩個 ``||Blocks:方塊 輸出||`` 方塊，並將它們放在 ``||Blocks:方塊 填充||`` 方塊之後。  
在第一個 ``||Blocks:方塊 輸出||`` 方塊中輸入 **"W"**，並在第二個 ``||Blocks:方塊 輸出||`` 方塊中輸入 **"E"**，以表示西和東。

## 第六步  
選擇用來印出字母的方塊。在這個範例中，**淺綠色羊毛** 用於西，**黃色羊毛** 用於東。

## 第七步  
在 ``||Blocks:方塊 輸出||`` **"W"** 中，輸入 **(~-11 ~0 ~0)** 坐標。

在 ``||Blocks:方塊 輸出||`` **"E"** 中，輸入 **(~11 ~0 ~0)** 坐標。

### ~ tutorialhint
```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    GRAY_WOOL,
    pos(-10, 0, 0),
    pos(10, 0, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    LIME_WOOL,
    pos(-11, 0, 0),
    WEST
    )
    blocks.print(
    "E",
    YELLOW_WOOL,
    pos(11, 0, 0),
    WEST
    )
})
```

## 第八步  
重複步驟以製作北和南。將 ``||Blocks:方塊 填充||`` 方塊放入 ``||Player:玩家 在聊天指令為||`` 方塊內。

將 ``||Blocks:方塊 填充||`` 方塊中的 **草地** 更改為你想要的軸線材質。這個範例使用 **黑色羊毛** 作為軸線。

## 第九步  
在 **起點** 輸入 **(~0 ~-1 ~-10)**，並在 **終點** 輸入 **(~0 ~-1 ~10)**。這將沿著 **Z** 軸生成一條方塊線。

## 第十步  
拖出兩個 ``||Blocks:方塊 輸出||`` 方塊，並將它們放在最新的 ``||Blocks:方塊 填充||`` 方塊之後。

## 第十一步  
在第一個 ``||Blocks:方塊 輸出||`` 方塊中輸入 **"N"**，並在第二個 ``||Blocks:方塊 輸出||`` 方塊中輸入 **"S"**，以表示北和南。

## 第十二步  
選擇用來印出字母的方塊。這個範例使用 **藍色羊毛** 用於北，**紅色羊毛** 用於南。

## 第十三步  
在 ``||Blocks:方塊 輸出||`` **"N"** 中，輸入 **(~0 ~0 ~-11)** 坐標。

在 ``||Blocks:方塊 輸出||`` **"S"** 中，輸入 **(~0 ~0 ~11)** 坐標。

### ~ tutorialhint
```blocks
player.onChat("compassrose", function () {
    blocks.fill(
    GRAY_WOOL,
    pos(-10, -1, 0),
    pos(10, -1, 0),
    FillOperation.Replace
    )
    blocks.print(
    "W",
    LIME_WOOL,
    pos(-11, 0, 0),
    WEST
    )
    blocks.print(
    "E",
    YELLOW_WOOL,
    pos(11, 0, 0),
    WEST
    )
    blocks.fill(
    GRAY_WOOL,
    pos(0, -1, -10),
    pos(0, -1, 10),
    FillOperation.Replace
    )
    blocks.print(
    "N",
    BLUE_WOOL,
    pos(0, 0, -11),
    WEST
    )
    blocks.print(
    "S",
    RED_WOOL,
    pos(0, 0, 11),
    WEST
    )
})
```
