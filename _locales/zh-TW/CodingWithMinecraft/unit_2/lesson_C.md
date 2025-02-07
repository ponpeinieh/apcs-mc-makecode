### @explicitHints 1

# 連結的牆

## 第一步  
快速開始。你已經獲得了一些用於此活動的起始代碼。現在添加一個新的 ``||Player:玩家 在聊天指令為||`` 事件處理器。將 **"jump"** 更改為 **"wall"**。

```template
let PlayerPosition: Position = null
let from_position: Position = null
let to_position: Position = null
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    pos(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    pos(-6, 13, 0)
    )
})
```

## 第二步  
建造一堵牆：從 ``||Blocks:方塊||`` 工具箱中，將 ``||Blocks:方塊 填充||`` 方塊放在 ``||Player:玩家 在聊天指令為 "wall"||`` 方塊內。

## 第三步  
調整一些內容：將 ``||Blocks:方塊 填充||`` 方塊中的 **草地** 更改為 **玻璃**。

## 第四步  
從 ``||Variables:變數||`` 工具箱中，將 ``||Variables:from_position||`` 拖曳到 ``||Blocks:方塊 填充||`` 方塊的 **起點** 位置。

## 第五步  
接著，將 ``||Variables:to_position||`` 拖曳到 ``||Blocks:方塊 填充||`` 方塊的 **終點** 位置。在 Minecraft 中試試這個指令。

### ~ tutorialhint
```blocks
player.onChat("wall", function () {
    blocks.fill(
    GLASS,
    from_position,
    to_position,
    FillOperation.Replace
    )
})
```

## 第六步  
當方塊被破壞時做出反應。從 ``||Blocks:方塊||`` 工具箱中，將 ``||Blocks:方塊 在被破壞時||`` 方塊拖曳到工作區。

## 第七步  
將 **草地** 更改為 **玻璃**。

## 第八步  
從 ``||Blocks:方塊||`` 工具箱中，將 ``||Blocks:方塊 放置於||`` 方塊放入 ``||Blocks:方塊 在被破壞時||`` 方塊內。

## 第九步  
將 **草地** 更改為 **鑽石**。

### ~ tutorialhint
```blocks
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, pos(0, 0, 0))
})
```

## 第十步  
修正位置代碼。將 ``||Positions:座標 隨機取值||`` 方塊放入 ``||Blocks:方塊 放置鑽石||`` 方塊中。

## 第十一步  
將 ``||Variables:from_position||`` 放入 **起點** 位置。

將 ``||Variables:to_position||`` 放入 **終點** 位置。

### ~ tutorialhint
```blocks
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, randpos(
    from_position,
    to_position
    ))
})
```

## 第十二步  
複製 ``||Blocks:方塊 在被玻璃破壞時||`` 方塊並更改一些內容。將 **玻璃** 更改為 **鑽石**。

## 第十三步  
然後將 ``||Blocks:方塊 放置鑽石||`` 更改為 ``||Blocks:方塊 放置橙色羊毛||``。現在在 Minecraft 中試試看吧。

### ~ tutorialhint
```blocks
let to_position: Position = null
let from_position: Position = null
let PlayerPosition: Position = null
blocks.onBlockBroken(GLASS, function () {
    blocks.place(DIAMOND_BLOCK, randpos(
    from_position,
    to_position
    ))
})
blocks.onBlockBroken(DIAMOND_BLOCK, function () {
    blocks.place(ORANGE_WOOL, randpos(
    from_position,
    to_position
    ))
})
player.onChat("wall", function () {
    blocks.fill(
    GLASS,
    from_position,
    to_position,
    FillOperation.Replace
    )
})
player.onChat("position", function () {
    PlayerPosition = player.position()
    from_position = positions.add(
    PlayerPosition,
    pos(6, 0, 0)
    )
    to_position = positions.add(
    PlayerPosition,
    pos(-6, 13, 0)
    )
})
```
