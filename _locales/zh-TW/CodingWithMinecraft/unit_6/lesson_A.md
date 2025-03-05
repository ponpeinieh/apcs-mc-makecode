### @explicitHints 1

# 活動：信仰之躍小遊戲

## 第一步  
點擊工具箱中的 **進階** 標籤以顯示更多工具箱類別。

在 ``||Functions:函數||`` 工具箱抽屜中，點擊 **創建函數** 按鈕。將函數命名為 **pool**，然後點擊 **確定**。

## 第二步  
創建 **platform()** 和 **teleport()** 函數。重複上一步驟，創建兩個名為 **platform** 和 **teleport** 的函數。

## 第三步  
將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到工作區。將此 ``||Player:玩家 在聊天指令為||`` 重命名為 **"play"**。

## 第四步  
將三個方塊 ``||Functions:呼叫函數 pool||``、``||Functions:呼叫函數 platform||``、``||Functions:呼叫函數 teleport||`` 放入 ``||Loops:當啓動時||`` 方塊中。

### ~ tutorialhint
```blocks
pool()
platform()
teleport()
function pool(){}
function platform(){}
function teleport(){}
```

## 第五步  
``||Loops:當啓動時||`` 方塊在程式啟動時運行。如果你在測試代碼或想重新啟動程式，這可能會有點麻煩。在這些情況下，請使用左下角的按鈕來重新啟動你的代碼。點擊代碼連接窗口左下角的停止按鈕。

## 第六步  
填充水池。將 ``||Blocks:方塊 填充||`` 方塊拖曳到 ``||Functions:pool||`` 函數中。``||Blocks:方塊 填充||`` 將從第一組坐標到第二組坐標填充一個三維方塊。

## 第七步  
在 ``||Blocks:方塊 填充||`` 的下拉選單中，選擇 **水** 方塊。

在 ``||Blocks:方塊 填充||`` 中，輸入以下值作為第一組起點坐標：**(0, -1, 0)**，並輸入 **(2, -3, 2)** 作為第二組終點坐標。

### ~ tutorialhint
```blocks
function pool() {
    blocks.fill(
    WATER,
    pos(0, -1, 0),
    pos(2, -3, 2),
    FillOperation.Replace
    )
}
pool()
```

## 第八步  
建造平台。將另一個 ``||Blocks:方塊 填充||`` 方塊拖曳到 ``||Functions:platform||`` 函數中。在 ``||Blocks:方塊 填充||`` 的下拉選單中，選擇 **雙層木質半磚**。

## 第九步  
在 ``||Blocks:方塊 填充||`` 方塊中，輸入以下值作為第一組起點坐標：**(1, 64, 1)**。

輸入以下值作為第二組終點坐標：**(3, 64, 3)**。

### ~ tutorialhint
```blocks
function platform() {
    blocks.fill(
    DOUBLE_WOODEN_SLAB,
    pos(1, 64, 1),
    pos(3, 64, 3),
    FillOperation.Replace
    )
}
platform()
```

## 第十步  
傳送自己。最後一步是將玩家傳送到平台正上方的一個位置。將一個 ``||Player:玩家 傳送到||`` 方塊拖曳到 ``||Functions:teleport||`` 函數中。

## 第十一步  
在 ``||Player:玩家 傳送到||`` 方塊中，輸入以下坐標值：**(2, 65, 2)**。

## 第十二步  
將遊戲模式設置為生存模式，方法是進入 ``||Gameplay:遊戲||`` 並拖出一個 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊。試試你的小遊戲吧！

### ~ tutorialhint
```blocks
function teleport() {
    player.teleport(pos(2, 65, 2))
    gameplay.setGameMode(
        SURVIVAL,
        mobs.target(LOCAL_PLAYER)
    )
}
teleport()
```

## 第十三步  
找到一塊空地。記住，因為你的遊戲基本上是在 ``||Loops:當啓動時||`` 迴圈執行時開始的，你可能需要啟動和停止代碼來重置它。然後來一次信仰之躍吧！記住，當你在平台上時，按住 **Shift** 鍵移動可以防止你掉下去，同時尋找一個合適的位置跳下。

點擊代碼連接窗口左下角的停止按鈕。

## 第十四步  
重新啟動編碼環境。點擊播放按鈕。如果播放按鈕未開啟，則你的代碼將不會在 Minecraft 中運行。

### ~ tutorialhint
```blocks
function pool() {
    blocks.fill(
    WATER,
    pos(0, -1, 0),
    pos(2, -3, 2),
    FillOperation.Replace
    )
}
function teleport() {
    player.teleport(pos(2, 65, 2))
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
}
function platform() {
    blocks.fill(
    DOUBLE_WOODEN_SLAB,
    pos(1, 64, 1),
    pos(3, 64, 3),
    FillOperation.Replace
    )
}
pool()
platform()
teleport()
```
