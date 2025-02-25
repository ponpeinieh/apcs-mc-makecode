### @explicitHints 1

# 活動：雞群風暴

## 第一步  
將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到編碼工作區，並將指令更改為 **"chickens"**。

## 第二步  
在 ``||Player:玩家 在聊天指令為 "chickens"||`` 方塊內添加一個 ``||Loops:重複||`` 迴圈。

## 第三步  
在 ``||Loops:重複||`` 迴圈內添加一個 ``||Mobs:生物 生成 動物||`` 方塊。

## 第四步  
將 ``||Mobs:生物 生成 動物||`` 方塊中的 **Y** 坐標更改為 **10**。雞會在玩家頭頂上方 10 格的位置生成。

### ~ tutorialhint
```blocks
player.onChat("chickens", function () {
    for (let index = 0; index < 4; index++) {
        mobs.spawn(CHICKEN, pos(0, 10, 0))
    }
})
```

## 第五步  
點擊 **"chickens"** 指令右側的 **加號(+)**。另一個下拉選單應該會出現，頂部顯示 **num1**。**num1** 是一個數字變數，你可以在代碼中使用它。

## 第六步  
更多雞！從 ``||Variables:變數||`` 中，將 ``||Loops:重複||`` 迴圈中的數字 **4** 替換為 ``||Variables:變數 num1||``。

進入 Minecraft，按下 **T** 打開聊天窗口，並在聊天窗口中輸入 **chickens 15**，變數 **num1** 將會取值為 **15**。

### ~ tutorialhint
```blocks
player.onChat("chickens", function (num1) {
    for (let i = 0; i < num1; i++) {
        mobs.spawn(CHICKEN, pos(0, 10, 0))
    }
})
```
