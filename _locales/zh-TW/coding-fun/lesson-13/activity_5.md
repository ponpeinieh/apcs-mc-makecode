### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 讓它下雨吧！

## 步驟 1
在 Minecraft 中跳舞時讓它下雨！為了實現這個目標，你需要使用幾個事件處理器。 1. 創建你的變數，例如：**walk**（走路）、**jump**（跳躍）和/或 **break**（破壞）。 2. 選擇事件處理器，例如 ``||player: 玩家 在行動方式為 墜落(fall) 時||``、``||player: 玩家 在行動方式為 走路(walk) 時||``。 3. 將你的新 ``||variable:變數||`` 設置為 ``||logic:true||`` 在每個對應的事件方塊內。 4. 使用 ``||loops: 無窮迴圈||`` 方塊，並拖動 ``||logic: 如果 那麽||`` 方塊進入其中。將條件設置為**是否所有以上變數皆爲** ``||logic: true||``(使用**並且**串聯條件)，在``||logic: 如果 那麽||``中添加 ``||gameplay: 遊戲 天氣設爲||`` 方塊設置為 **下雨(rain)**。

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
