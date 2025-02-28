### @explicitHints 1

# 活動：墜落感應器

## 第一步  
將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到工作區。

## 第二步  
右鍵點擊 ``||Player:玩家 在聊天指令為||`` 並選擇複製。重複此操作兩次，最終你會得到三個 ``||Player:玩家 在聊天指令為||`` 方塊。

## 第三步  
將這些指令命名為 **"cr"**（創造模式）、**"su"**（生存模式）和 **"pm"**（墜落報告）。

## 第四步  
拖出兩個事件方塊：``||Player:玩家 在行動方式為 走路(walk) 時||`` 和 ``||Player:玩家 在死亡時||``。

## 第五步  
將 ``||Player:玩家 在行動方式為 走路(walk) 時||`` 更改為 ``||Player:玩家 在行動方式為 墜落(fall) 時||`` 方塊。

### ~ tutorialhint
```blocks
player.onChat("cr", function () {

})
player.onChat("su", function () {

})
player.onTravelled(TravelMethod.Walk, function () {

})
player.onChat("pm", function () {

})
player.onDied(function () {

})
```

## 第六步  
進入「創造模式」。構建 **"cr"** 的 ``||Player:玩家 在聊天指令為||``。這個指令會將遊戲模式更改為創造模式。在創造模式下你可以飛行，這對於到達高處非常有幫助。

## 第七步  
將 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊拖曳到 ``||Player:玩家 在聊天指令為 "cr"||`` 方塊內。

## 第八步  
在 ``||Gameplay:遊戲 更改遊戲模式||`` 中，選擇 **創造模式**，並將 ``||Mobs:目標||`` 更改為 **自己 @s**。

### ~ tutorialhint
```blocks
player.onChat("cr", function () {
    gameplay.setGameMode(
    CREATIVE,
    mobs.target(LOCAL_PLAYER)
})
```

## 第九步  
進入「生存模式」。將 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊拖曳到 ``||Player:玩家 在聊天指令為 "su"||`` 方塊內。

## 第十步  
在 ``||Gameplay:遊戲 更改遊戲模式||`` 中，選擇 **生存模式**，將 ``||Mobs:目標||`` 更改為 **自己 @s**。

### ~ tutorialhint
```blocks
player.onChat("su", function () {
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
})
```

## 第十一步  
在 ``||Variables:變數||`` 中，點擊 **創建變數**，並將新變數命名為 ``||Variables:fall||``。這個變數會隨著玩家墜落時每墜落一格而遞增（累加）。

## 第十二步  
記錄墜落高度。在 ``||Variables:變數||`` 中，點擊 **創建變數**，並將新變數命名為 ``||Variables:report||``。

## 第十三步  
將 ``||Variables:變數 改變||`` 方塊放入 ``||Player:玩家 在行動方式為 墜落(fall) 時||`` 事件中。

## 第十四步  
在 ``||Variables:變數 改變||`` 方塊中，選擇變數 **fall** 。

## 第十五步  
拖出 ``||Variables:變數 設爲||`` 方塊。右鍵點擊並複製一次。現在你應該有兩個這樣的方塊。

將其中一個 ``||Variables:變數 設爲||`` 方塊放入 ``||Player:玩家 在死亡時||`` 事件中。

## 第十六步  
在這個 ``||Variables:變數 設爲||`` 方塊中，選擇 **report** 。

## 第十七步  
將 **fall** 拖曳到第二個欄位中，替換 **0**，使方塊顯示為 **將 report 設為 fall**。

## 第十八步  
重置墜落計數。將你在第十五步複製的另一個 ``||Variables:變數 設為||`` 方塊移動到 ``||Player:玩家 在死亡時||`` 事件的最下方。將變數更改為 **fall**。

### ~ tutorialhint
```blocks
let fall = 0
let report = 0
player.onDied(function () {
    report = fall
    fall = 0
})
player.onTravelled(TravelMethod.Fall, function () {
    fall += 1
})
```

## 第十九步  
報告你的墜落高度。將 ``||Player:玩家 説出||`` 方塊放入 ``||Player:玩家 在聊天指令為 "pm"||`` 方塊中。

## 第二十步  
點擊 **進階** 以顯示 ``||Text:文字||`` 工具箱類別。

將 ``||Text:合併||`` 方塊拖曳到 ``||Player:玩家 説出||`` 方塊中，替換 **"Hi!"**。

### ~ tutorialhint
```blocks
let report = 0
player.onChat("pm", function () {
    player.say("Hello" + "World")
})
```

## 第二十一步  
將變數與訊息合併。在 ``||Text:合併||`` 的第一個欄位中，輸入 **"你墜落了"**，替換 *"Hello"*。

## 第二十二步  
將 ``||Variables:report||`` 拖曳到 ``||Text:合併||`` 的第二個欄位中，替換 *"World"*。

### ~ tutorialhint
```blocks
let report = 0
player.onChat("pm", function () {
    player.say("你墜落了 " + report)
})
```
 