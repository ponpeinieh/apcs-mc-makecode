### @explicitHints 1

# 六便士之歌

## 第一步  
檢查方塊是否被破壞。從 ``||Blocks:方塊||`` 工具箱中，將 ``||Blocks:方塊 在被破壞的方塊為時||`` 編碼指令拖曳到工作區。

### ~ tutorialhint
```blocks
blocks.onBlockBroken(GRASS, function () {
	
})
```

## 第二步  
選擇 **蛋糕**。使用下拉選單，選擇 **蛋糕** 物品。

## 第三步  
生成一隻動物。從 ``||Mobs:生物||`` 工具箱中，將 ``||Mobs:生物 生成 動物||`` 方塊放在 ``||Blocks:方塊 在被破壞的方塊為時||`` 方塊下方，直到看到它卡入位置。

### ~ tutorialhint     
```blocks
blocks.onBlockBroken(CAKE, function () {
    mobs.spawn(CHICKEN, pos(0, 0, 0))
})
```

## 第四步  
生成一隻鸚鵡。在 ``||Mobs:生物 生成 動物||`` 方塊的下拉選單中，選擇 **鸚鵡**，並將 **Y** 坐標更改為 **1**。

## 第五步  
添加更多鸚鵡。從 ``||Loops:迴圈||`` 工具箱中，將 ``||Loops:重複||`` 迴圈放在 ``||Mobs:生物 生成 動物||`` 方塊周圍。在 ``||Loops:重複||`` 迴圈中，輸入數字 **24**。

### ~ tutorialhint
```blocks
blocks.onBlockBroken(CAKE, function () {
    for (let index = 0; index < 24; index++) {
        mobs.spawn(CHICKEN, pos(0, 1, 0))
    }
})
```

## 第六步  
運行代碼。要在遊戲中運行此代碼，請將蛋糕添加到你的玩家物品欄中（按 E 打開物品欄），在工具欄中選擇蛋糕（使用鼠標滾輪或數字鍵），然後右鍵單擊將蛋糕放置在地面上。接著切換回徒手狀態，並使用左鍵單擊破壞蛋糕——你應該會看到一群鸚鵡出現！
