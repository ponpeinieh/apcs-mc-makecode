### @explicitHints 1

# 活動：殭屍豬人

## 第一步  
創建一個函數。點擊工具箱中的 **進階** 標籤以顯示更多工具箱類別。

將此函數命名為 **zombiepig**，然後點擊 **確定**。

## 第二步  
創建 **platform()** 和 **teleport()** 函數。重複上一步驟，創建兩個名為 **atmosphere** 和 **setup** 的函數。

## 第三步  
將 ``||Player:玩家 在聊天指令為||`` 方塊拖曳到工作區。

將此 ``||Player:玩家 在聊天指令為||`` 重命名為 **"play"**。

## 第四步  
將三個方塊 ``||Functions:呼叫函數 setup||``、``||Functions:呼叫函數 atmosphere||``、``||Functions:呼叫函數 zombiepig||`` 放入 ``||Player:玩家 在聊天指令為 "play"||`` 方塊中。

### ~ tutorialhint
```blocks
function zombiepig()  {

}
function atmosphere()  {

}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
```

## 第五步  
創建殭屍豬人。將一個 ``||Mobs:生物 生成 動物||`` 方塊拖曳到 ``||Functions:zombiepig||`` 函數中。從下拉選單中選擇 **豬** 來更改動物。然後更改 Z 坐標的位置，使豬生成在玩家北邊五格的位置。

創建另一個生成方塊並將其放在第一個方塊下方。將 **動物** 替換為 **閃電電流**。

## 第六步  
輸入與豬相同的坐標：**(~0, ~0, ~-5)**。這裡的技巧是，如果豬被閃電擊中，它會變成殭屍豬人！這就是為什麼你希望兩者在相同坐標 **(~0, ~0, ~-5)** 生成。

### ~ tutorialhint
```blocks
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
function setup()  {

}
function atmosphere()  {

}
```

## 第七步  
調整設置。你希望遊戲自動運行。輸入 **play** 後，遊戲應該開始並設置好一切，這樣你就可以與瘋狂的殭屍豬人戰鬥了。第一個問題是遊戲的難度等級。如果遊戲設置為和平模式，豬不會變成殭屍豬人。

## 第八步  
將一個 ``||Gameplay:遊戲 設置難度為||`` 方塊拖曳到 ``||Functions:setup||`` 函數中。

調整此新方塊，使其顯示為 ``||Gameplay:遊戲 設置難度為 '簡單'||``。

## 第九步  
接下來，你希望更改玩家的遊戲模式。將遊戲模式設置為生存模式，確保殭屍豬人會追擊你！只要你攻擊殭屍豬人，它就會開始反擊！將一個 ``||Gameplay:遊戲 更改遊戲模式||`` 方塊拖曳到 ``||Functions:setup||`` 函數中。

調整此新方塊，使其顯示為 ``||Gameplay:遊戲 更改遊戲模式為 '生存'||``。

同時，調整目標以選擇 **自己**。

## 第十步  
最後，沒有武器的戰鬥將非常困難。你可以給自己一把武器，使遊戲對玩家更合理。抓取一個 ``||Mobs:生物 給予||`` 方塊，並將其作為 ``||Functions:setup||`` 函數中的最後一個方塊。

## 第十一步  
你需要選擇自己並給自己一把劍或其他武器。範例中給了一把鑽石劍。

### ~ tutorialhint
```blocks
function atmosphere()  {

}
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

## 第十二步  
此時，你可以測試你的遊戲！在聊天窗口中輸入 **play**，小遊戲將開始。

## 第十三步  
調整時間。這個小遊戲的最後一步是通過調整時間來添加視覺效果。這將為所有殭屍提供合適的氛圍。你將添加一個 **時間設置** 方塊。

## 第十四步  
Minecraft 的一天持續 24,000 刻，相當於 20 分鐘的遊戲時間。通過將遊戲時間設置為午夜，你將當前時間設置為午夜開始的時間。時間設置方塊是一種簡單的方法，可以將時間移動到一天的常見部分。午夜等於 18,000 刻（12:00 AM）。

## 第十五步  
將一個 ``||Gameplay:遊戲 時間設置||`` 方塊拖曳到 ``||Functions:atmosphere||`` 函數中。

調整此方塊，使其顯示為 ``||Gameplay:遊戲 時間設置為 '午夜'||``。在 Minecraft 中試試看吧！

### ~ tutorialhint
```blocks
function atmosphere() {
    gameplay.timeSet(gameplay.time(MIDNIGHT))
}
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```

## 第十六步  
時間沒有改變？確保 **永遠白天** 選項未開啟。

生成更多殭屍豬人。擊敗一個殭屍豬人後，你希望生成另一個殭屍豬人。你可以使用 ``||Mobs:生物 在被擊殺時||`` 事件來創建一個新的殭屍豬人。你將使用函數 ``||Functions:呼叫函數 zombiepig||``。

## 第十七步  
抓取一個 ``||Mobs:生物 在被擊殺時||`` 事件並將其放在工作區。

調整此方塊，使其顯示為 ``||Mobs:生物 在被擊殺的怪物為 殭屍豬人 時||``。

## 第十八步  
在此新事件中添加一個 ``||Functions:呼叫函數 zombiepig||``。

### ~ tutorialhint
```blocks
function setup() {
    gameplay.setDifficulty(EASY)
    gameplay.setGameMode(
    SURVIVAL,
    mobs.target(LOCAL_PLAYER)
    )
    mobs.give(
    mobs.target(LOCAL_PLAYER),
    blocks.item(DIAMOND_SWORD),
    1
    )
}
mobs.onMobKilled(mobs.monster(PIG_ZOMBIE), function () {
    zombiepig()
})
function atmosphere() {
    gameplay.timeSet(gameplay.time(MIDNIGHT))
}
function zombiepig() {
    mobs.spawn(PIG, pos(0, 0, -5))
    mobs.spawn(LIGHTNING_BOLT, pos(0, 0, -5))
}
player.onChat("play", function () {
    setup()
    atmosphere()
    zombiepig()
})
```
 