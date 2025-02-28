### @explicitHints 1

# 活動：箭矢計數器

## 第一步  
創建一個新的變數並將其命名為 **arrows**。

## 第二步  
記錄射出的箭矢。將 ``||Player:玩家 在射箭時||`` 方塊拖曳到工作區。

## 第三步  
將 ``||Variables:變數 改變||`` 方塊放入 ``||Player:玩家 在射箭時||`` 方塊內。

## 第四步  
在 ``||Variables:變數 改變||`` 方塊中，選擇 ``||Variables:變數 arrows||``。

## 第五步  
組合文字：點擊工具箱中的 **進階** 類別以顯示 ``||Text:文字||`` 工具箱抽屜。將 ``||Text:合併||`` 方塊拖曳到 ``||Player:玩家 説出||`` 方塊中，替換 **"Hi"** 字串。

### ~ tutorialhint
```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("Hello" + "World")
})
```

## 第六步  
將變數與訊息合併。在 ``||Text:合併||`` 的第一個欄位中，輸入 **"射出的箭矢："**。

## 第七步  
從 ``||Variables:變數||`` 中，將 **arrows** 變數拖曳到 ``||Text:合併||`` 的第二個欄位中，替換字串 **"World"**。這個方塊會將字串 **"射出的箭矢："** 與數字變數合併。每次射箭時，``||Player:玩家 説出||`` 會在畫面頂部顯示訊息。

### ~ tutorialhint
```blocks
let arrows = 0
player.onArrowShot(function () {
    arrows += 1
    player.say("射出的箭矢：" + arrows)
})
```

## 第八步  
試試看！進入 Minecraft 並測試它！在聊天窗口中輸入以下指令來獲得弓和箭：
* /give @p bow
* /give @p arrow 64
