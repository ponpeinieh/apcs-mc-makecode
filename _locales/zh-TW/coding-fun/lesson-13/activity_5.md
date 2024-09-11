### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 讓它下雨吧！

## 步驟 1
在 Minecraft 中跳舞時讓它下雨！要實現這個效果，你需要使用幾個事件處理器。以下是步驟：

1. 創建幾個變數，例如：**walk**（走路）、**jump**（跳躍）。
2. 選擇事件處理器，比如  ``||player: 玩家 在行動方式為 走路(walk) 時||``和``||player: 玩家 在行動方式為 墜落(fall) 時||`` 。
3. 在每個對應的事件方塊內，將你的新 ``||variable:變數||`` 設置為 ``||logic:true||``。
4. 使用 ``||loops: 無限迴圈||`` 方塊，然後將 ``||logic: 如果 那麽||`` 方塊拖入其中。將條件設置為**所有上述變數皆為** ``||logic: true||`` （使用 **且** 來串聯）。接著，在 ``||logic: 如果 那麽||`` 中添加 ``||gameplay: 遊戲 天氣設爲||`` 方塊，並設置天氣為 **下雨(rain)**。

### ~ tutorialHint
```blocks
let walk = false
player.onTravelled(WALK, function () {
    walk = true
})
loops.forever(function () {
    if (walk == true && "" == "") {
    	
    }
})

```

```ghost
let climb = false
let walk = false
let _break = false
player.onTravelled(CLIMB, function () {
    climb = true
})
player.onTravelled(WALK, function () {
    walk = true
})
blocks.onBlockBroken(STONE, function () {
    _break = true
})
loops.forever(function () {
    if (walk == true && climb == (true && _break == true)) {
        gameplay.setWeather(RAIN)
    }
})
```
