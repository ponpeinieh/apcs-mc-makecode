### @explicitHints 1

# 活動：自動農場

## 第一步  
將 ``||Player:玩家 在行動方式為 走路(walk) 時||`` 方塊拖曳到工作區。

將 ``||Mobs:生物 生成||`` 方塊放入 ``||Player:玩家 在行動方式為 走路(walk) 時||`` 方塊中。在 ``||Mobs:生物 生成||`` 方塊中選擇 **羊** 或其他你想養的動物。

## 第二步  
在 ``||Mobs:生物 生成||`` 方塊中輸入坐標 **(~0, ~0, ~1)**。羊會在玩家南邊一格的位置生成，沿著 **Z** 軸。

### ~ tutorialhint
```blocks
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
```

## 第三步  
開始建造羊圈。將一個新的 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到工作區，並將指令更改為 **"pen"**。

## 第四步  
將 ``||Blocks:方塊 填充||`` 方塊放入 ``||Player:玩家 在聊天指令為 "pen"||`` 方塊中。

將 ``||Blocks:方塊 填充||`` 方塊的材質更改為 **地獄磚柵欄**，並將坐標更改為 **~5, ~0, ~1** 和 **~-5, ~4, ~1**。

### ~ tutorialhint
```blocks
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    pos(5, 0, 1),
    pos(-5, 4, 1),
    FillOperation.Replace
    )
})
```

## 第五步  
建立側牆。右鍵點擊用來建造南牆的 ``||Blocks:方塊 填充||`` 方塊並複製兩次。這些新的複製方塊將用來建造側牆。

## 第六步  
調整側牆的材質。一側可以使用 **相思木柵欄**，另一側可以使用 **樺木柵欄**。

## 第七步  
調整 **相思木柵欄** 的坐標為 **~5, ~0, ~1** 和 **~-5, ~4, ~20**；**樺木柵欄** 的坐標為 **~5, ~0, ~1** 和 **~-5, ~4, ~20**。

### ~ tutorialhint
```blocks
player.onTravelled(WALK, function () {
    mobs.spawn(SHEEP, pos(0, 0, 1))
})
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    pos(5, 0, 1),
    pos(-5, 4, 1),
    FillOperation.Replace
    )
    blocks.fill(
    BIRCH_FENCE,
    pos(-5, 0, 1),
    pos(-5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    ACACIA_FENCE,
    pos(5, 0, 1),
    pos(5, 4, 20),
    FillOperation.Replace
    )
})
```

## 第八步  
關閉羊圈的北側入口。**Z** 坐標應與南牆相距 **20** 格，因為這是側牆的長度。在 Minecraft 中試試看，並生成任意數量的羊吧！

### ~ tutorialhint
```blocks
player.onChat("pen", function () {
    blocks.fill(
    NETHER_BRICK_FENCE,
    positions.create(5, 0, -1),
    positions.create(-5, 4, -1),
    FillOperation.Replace
    )
    blocks.fill(
    ACACIA_FENCE,
    positions.create(-5, 0, -1),
    positions.create(-5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    BIRCH_FENCE,
    positions.create(5, 0, -1),
    positions.create(5, 4, 20),
    FillOperation.Replace
    )
    blocks.fill(
    NETHER_BRICK_FENCE,
    positions.create(5, 0, 20),
    positions.create(-5, 4, 20),
    FillOperation.Replace
    )
})
```
