### @explicitHints 1

# 活動：Minecraft 搬家公司

## 第一步  
將三個 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到編碼工作區。

將這些 ``||Player:玩家 在聊天指令為||`` 方塊的名稱更改為 **"start"**、**"stop"** 和 **"copy"**。

### ~ tutorialhint
```blocks
player.onChat("start", function () { })
player.onChat("stop", function () { })
player.onChat("copy", function () { })
```

## 第二步  
創建變數。打開 ``||Variables:變數||`` 並點擊 **創建變數** 按鈕。

將變數命名為 **start**，然後點擊 **確定**。

## 第三步  
創建另一個變數並將其命名為 **stop**，然後點擊 **確定**。

## 第四步  
設定變數。將 ``||Variables:變數 設為||`` 方塊放入 **start** 的 ``||Player:玩家 在聊天指令為||`` 方塊中。

使用下拉選單將其調整為 ``||Variables:變數 start 設為||`` **0**。

## 第五步  
將 **0** 更改為 ``||Player:玩家 世界位置||``。將 ``||Player:玩家 世界位置||`` 拖曳到 ``||Variables:變數 start 設為||`` 中，並替換 **0**。

### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
})
```

## 第六步  
輸出訊息。在 ``||Variables:變數 start 設為||`` 之後添加 ``||Player:玩家 説出||`` 方塊。

### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("Hi!")
})
```

## 第七步  
打開 ``||Text:文字||``，將 ``||Text:合併||`` 方塊放入 ``||Player:玩家 説出||`` 方塊中，替換 **"Hi!"**。

在 ``||Text:合併||`` 的第一個欄位中，輸入 **"起點已設定"**。

## 第八步  
接著，打開 ``||Variables:變數||``，將 ``||Variables:變數 start||`` 拖曳到 ``||Text:合併||`` 的第二個欄位中。

### ~ tutorialhint
```blocks
let start: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("起點已設定: " + start)
})
```

## 第九步  
重複步驟以設定停止指令。右鍵點擊 ``||Player:玩家 在聊天指令為||`` **"start"** 並複製它。將 ``||Player:玩家 在聊天指令為||`` 的名稱更改為 **stop**。

將 ``||Player:玩家 説出||`` 的文字更改為 **"終點已設定"**。將 ``||Variables:變數 stop||`` 放入 ``||Text:合併||`` 方塊中。

### ~ tutorialhint
```blocks
let stop: Position = null
player.onChat("stop", function () {
    stop = player.position()
    player.say("終點已設定: " + stop)
})
```

## 第十步  
刪除空的 ``||Player:玩家 在聊天指令為||`` 方塊 **"stop"** 和 **"copy"**。

## 第十一步  
建立複製指令。打開 ``||Blocks:方塊||``，將 ``||Blocks:方塊 複製||`` 方塊拖曳到 **"copy"** 方塊中。

### ~ tutorialhint
```blocks
player.onChat("copy", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 第十二步  
從 ``||Variables:變數||`` 中，將 ``||Variables:變數 start||`` 拖曳到 ``||Blocks:方塊 複製||`` 方塊的第一個欄位中。你的方塊現在應該顯示為 **複製 起點**。

## 第十三步  
從 ``||Variables:變數||`` 中，將 ``||Variables:變數 stop||`` 拖曳到 ``||Blocks:方塊 複製||`` 方塊的第二個欄位中。你的方塊現在應該顯示為 **複製 起點 到 終點**。

### ~ tutorialhint
```blocks
player.onChat("copy", function () {
    let stop: Position = null
    let start: Position = null
    blocks.clone(
    start,
    stop,
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 第十四步  
在 Minecraft 中測試你的代碼。你需要建造一個你想複製的房子或結構。將你的玩家移動到結構的一個底部角落，然後在聊天窗口中輸入指令 **"start"**。

## 第十五步  
將你的玩家從起點對角移動到頂部角落。在聊天窗口中輸入指令 **"stop"**。  
將你的玩家移動到世界中你想複製結構的空曠位置，然後在聊天窗口中輸入指令 **"copy"**。  
它是否正確複製了你的房子或結構？

### ~ tutorialhint
```blocks
let start: Position = null
let stop: Position = null
player.onChat("start", function () {
    start = player.position()
    player.say("起點已設定: " + start)
})
player.onChat("copy", function () {
    blocks.clone(
    start,
    stop,
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
player.onChat("stop", function () {
    stop = player.position()
    player.say("終點已設定: " + stop)
})
```
