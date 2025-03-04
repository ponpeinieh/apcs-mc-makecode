### @explicitHints 1

# 活動：你幾歲？

## 第一步  
將現有的 ``||Player:玩家 在聊天指令為 "run"||`` 方塊重命名為 **"age"**。

點擊 ``||Player:玩家 在聊天指令為 "run"||`` 上的加號 **(+)**，以創建一個 **num1** 變數參數。

將 **num1** 重命名為 **FriendsAge**。這使你的代碼更易讀。在編碼時，請始終使用有意義的名稱來命名變數。這使得查找錯誤更加直觀。你可以從下拉選單中重命名變數。

### ~ tutorialhint
```blocks
player.onChat("age", function(FriendsAge) {

})
```

## 第二步  
使用條件判斷。將一個 ``||Logic:如果 那麽 否則||`` 方塊放入 ``||Player:玩家 在聊天指令為 "age"||`` 方塊內。

點擊 ``||Logic:如果 那麽 否則||`` 方塊上的加號 **(+)**，以創建另一個 ``||Logic:否則如果 那麽||`` 分支。

## 第三步  
插入比較條件。將一個 **小於**，``||Logic:0 < 0||``，比較方塊放入 ``||Logic:如果||`` 欄位中，替換 **true**。

## 第四步  
將一個 **等於**，``||Logic:0 = 0||``，比較方塊放入 ``||Logic:否則如果||`` 欄位中。

### ~ tutorialhint
```blocks
player.onChat("age", function (FriendsAge) {
    if (0 < 0) {
    } else if (0 == 0) {
    } else {
    }
})
```

## 第五步  
與你的變數進行比較。將兩個 ``||Variables:FriendsAge||`` 方塊拖曳到每個 **比較** 方塊的第一個欄位中。

在比較方塊的第二個欄位中，輸入你的年齡（例如 **12**）。

### ~ tutorialhint
```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {

    } else if (FriendsAge == 12) {

    } else {

    }
})
```

## 第六步  
為每個條件輸出方塊。將一個 ``||Blocks:方塊 輸出 "Hello"||`` 方塊拖曳到工作區。右鍵點擊 ``||Blocks:方塊 輸出 "Hello"||`` 方塊並選擇 **複製** 以創建一個副本。

將這些方塊分別放入 ``||Logic:如果||``、``||Logic:否則如果||`` 和 ``||Logic:否則||`` 分支中。

### ~ tutorialhint
```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    } else {
        blocks.print(
        "HELLO",
        GRASS,
        pos(0, 0, 0),
        WEST
        )
    }
})
```

## 第七步  
輸出不同的訊息。在每個 ``||Blocks:方塊 輸出 "Hello"||`` 方塊中，輸入不同的訊息，分別針對比你年輕、與你同齡或比你年長的人。

## 第八步  
使用 ``||Blocks:方塊 輸出||`` 方塊中的下拉選單，為每條訊息選擇不同的方塊。

在所有 ``||Blocks:方塊 輸出||`` 方塊中，將 **Y** 坐標設為 10（以便這些訊息在天空中輸出）。

### ~ tutorialhint
```blocks
player.onChat("age", function (FriendsAge) {
    if (FriendsAge < 12) {
        blocks.print(
        "Baby",
        SMOOTH_SANDSTONE,
        pos(0, 10, 0),
        WEST
        )
    } else if (FriendsAge == 12) {
        blocks.print(
        "Coincidence?",
        ORANGE_TERRACOTTA,
        pos(0, 10, 0),
        WEST
        )
    } else {
        blocks.print(
        "Grandpa",
        STONECUTTER,
        pos(0, 10, 0),
        WEST
        )
    }
})
```

## 第九步  
享受顯示年齡訊息的樂趣。與同伴一起運行這些訊息。在 Minecraft 遊戲中，按下 **T** 打開聊天窗口。

詢問你旁邊的人的年齡，並輸入 **age x** —— 其中 **x** 是你旁邊的人的年齡。

抬頭看看你上方的訊息吧！
