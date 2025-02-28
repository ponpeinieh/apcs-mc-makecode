### @explicitHints 1

# 活動：文字大師

## 第一步  
將 ``||Loops:當啓動時||`` 方塊拖曳到工作區。

打開 ``||Variables:變數||``，創建兩個新變數並將其命名為 **word1** 和 **word2**。將 ``||Variables:變數 設為||`` 方塊放入 ``||Loops:當啓動時||`` 方塊內。

## 第二步  
點擊 **進階** 以查看 ``||Text:文字||`` 工具箱類別。選擇 **" "** 並將其放入 ``||Variables:變數 設為||`` 方塊中，替換數字 **0**。你將把這個變數設為一個字串。

## 第三步  
使用 ``||Variables:變數 設為||`` 的下拉選單將 **item** 重命名為 **word1**。

右鍵點擊 ``||Variables:變數 word1 設為||`` 並複製它。將這個新的複製方塊放入 ``||Loops:當啓動時||`` 方塊內。

## 第四步  
現在回到第二個 ``||Variables:變數 word1 設為||`` 方塊，並從下拉選單中將 **word1** 更改為 **word2**。

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
word1 = ""
word2 = ""
```

## 第五步  
寫兩個有趣的詞！將 **word1** 的空字串 **" "** 替換為一些文字。

將 **word2** 的空字串 **" "** 替換為一些文字。以下是一個範例：將 **rail** 設為 ``||Variables:word1||``，將 **road** 設為 ``||Variables:word2||``。

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
word1 = "rail"
word2 = "road"
```

## 第六步  
印出 word1。將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到工作區。將指令命名為 **mix**。

將 ``||Blocks:方塊 輸出||`` 方塊拖曳到 ``||Player:玩家 在聊天指令為 mix||`` 方塊內。

## 第七步  
將 ``||Variables:word1||`` 放入 ``||Blocks:方塊 輸出||`` 方塊中。

將 **草地** 更改為 **紅石礦**。

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 0, 0),
    WEST
    )
})
word1 = "rail"
word2 = "road"
```

## 第八步  
設定 word2。複製 ``||Blocks:方塊 輸出||`` ``||Variables:word1||`` 方塊。

更改此方塊以輸出 ``||Variables:word2||``。將 **草地** 更改為 **紅石燈**。

## 第九步  
微調並測試。你需要在空中輸出文字以確保有足夠的空間容納所有內容。此外，你開始在 **南北軸** 上向 **南** 輸出文字。調整 ``||Blocks:方塊 輸出||`` 方塊，使其顯示為 **沿著南 (正 Z)**。

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
player.onChat("mix", function () {
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 0, 0),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 第十步  
你的兩個詞現在已經輸出了，但有一個小問題。如果你在輸入 **mix** 後沒有停止移動，兩個詞在輸出時將不會對齊。

## 第十一步  
為了解決這個問題，儲存玩家的世界位置。點擊 **創建變數** 並將新變數命名為 **Starting_World_Position**。

將 ``||Variables:變數 設為||`` 方塊添加到 ``||Player:玩家 在聊天指令為 mix||`` 方塊的頂部。將此方塊更改為 **將 Starting_World_Position 設為**。

## 第十二步  
將 ``||Player:玩家 世界位置||`` 放入 ``||Variables:變數 Starting_World_Position 設為||`` 方塊中。

### ~ tutorialhint
```blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    pos(0, 30, 0),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    pos(0, 20, 0),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 第十三步  
修正輸出方塊的位置。

### ~ tutorialhint
```blocks
let word2 = ""
let Starting_World_Position: Position = null
let word1 = ""
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    positions.add(
    Starting_World_Position,
    pos(0, 30, 0)
    ),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    positions.add(
    Starting_World_Position,
    pos(0, 20, 0)
    ),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```

## 第十四步  
合併並輸出。複製其中一個 ``||Blocks:方塊 輸出||`` 方塊，並將其放在 ``||Player:玩家 在聊天指令為 mix||`` 方塊的底部。

調整設置，使其使用 **紅石方塊** 輸出。

## 第十五步  
**Y** 相對坐標應為 **5**。

## 第十六步  
搜尋「合併」。將這個 ``||Text:文字||`` 方塊放入，使 ``||Blocks:方塊 輸出||`` 方塊顯示為 **輸出 合併 word1 word2**。

### ~ tutorialhint
```blocks
let word2 = ""
let word1 = ""
let Starting_World_Position: Position = null
player.onChat("mix", function () {
    Starting_World_Position = player.position()
    blocks.print(
    word1,
    REDSTONE_ORE,
    positions.add(
    Starting_World_Position,
    pos(0, 30, 0)
    ),
    SOUTH
    )
    blocks.print(
    word2,
    REDSTONE_LAMP,
    positions.add(
    Starting_World_Position,
    pos(0, 20, 0)
    ),
    SOUTH
    )
    blocks.print(
    word1 + word2,
    REDSTONE_BLOCK,
    positions.add(
    Starting_World_Position,
    pos(0, 5, 0)
    ),
    SOUTH
    )
})
word1 = "rail"
word2 = "road"
```
 