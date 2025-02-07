### @explicitHints 1

# 阿拉莫最後一戰

## 第一步  
回應生物被擊殺事件：從 ``||Mobs:生物||`` 工具箱抽屜中，將 ``||Mobs:生物 在被殺的是時||`` 方塊拖曳到編碼工作區。

### ~ tutorialhint
```blocks
mobs.onMobKilled(CHICKEN, function () {
})
```

## 第二步  
檢查是否為怪物：從 ``||Mobs:生物||`` 工具箱抽屜中，拖曳一個 ``||Mobs:怪物||`` 下拉方塊來替換預設的 **動物**。在 ``||Mobs:怪物||`` 方塊的下拉選單中，選擇 **殭屍** 生成蛋。

## 第三步  
準備生成新的殭屍！從 ``||Mobs:生物||`` 工具箱抽屜中，將 ``||Mobs:生物 生成 動物||`` 方塊拖曳到 ``||Mobs:生物 在被殺的是時||`` 事件處理方塊下方。

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
mobs.spawn(CHICKEN, pos(0, 0, 0))
})
```

## 第四步  
選擇殭屍生成蛋。類似於第二步的操作，這裡你需要將 ``||Mobs:生物 生成 動物||`` 方塊中的預設 **動物** 替換為 **殭屍**。

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
mobs.spawn(mobs.monster(ZOMBIE), pos(0, 0, 0))
})
```

## 第五步  
兩隻殭屍比一隻更好。你希望每擊殺一隻殭屍就生成兩隻殭屍，因此從 ``||Loops:迴圈||`` 工具箱抽屜中，將 ``||Loops:重複||`` 迴圈拖曳到工作區。這個 ``||Loops:重複||`` 迴圈應該放在 ``||Mobs:生物 在被殺的是時||`` 事件內，而你的 ``||Mobs:生物 生成||`` 方塊應該放在 ``||Loops:重複||`` 迴圈內。

在 ``||Loops:重複||`` 迴圈中，輸入數字 **2**。

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let index = 0; index < 2; index++) {
        mobs.spawn(mobs.monster(ZOMBIE), pos(0, 0, 0))
    }
})
```

## 第六步  
在哪裡生成殭屍？將預設的 **(~0 ~0 ~0)** 替換為 ``||Positions:座標 隨機取值||`` 方塊。

## 第七步  
設定隨機位置的範圍：在 ``||Positions:座標 隨機取值||`` 方塊中，將 **起點** 坐標設為 **(~10 ~0 ~10)**，並將 **終點** 坐標設為 **(~-10 ~0 ~-10)**。

### ~ tutorialhint
```blocks
mobs.onMobKilled(mobs.monster(ZOMBIE), function () {
    for (let i = 0; i < 2; i++) {
        mobs.spawn(mobs.monster(ZOMBIE), randpos(
            pos(10, 0, 10),
            pos(-10, 0, -10)
        ))
    }
})
```

## 第八步  
在遊戲中試試看吧！
