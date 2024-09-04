### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 啟動傳送門！

## 步驟 1
你需要在站在**金磚**上時讓閃電擊中。在開始時，首先``||loops: 當啓動時||``需要將``||gameplay: 天氣設爲||``設為下雨。然後在``||player: 在行動方式為 走路(walk) 時||``中放置``||logic: 如果 那麽||``, ``||blocks: 方塊 測試 位置||``和``||mobs: 生物 生成 彈射物 閃電電流 於||``來使閃電在正確的時刻擊中。

### ~ tutorialHint
金磚位於你下方的**0, -1, 0**座標。


```ghost
player.onTravelled(WALK, function () {
    if (blocks.testForBlock(GOLD_BLOCK, pos(0, -1, 0))) {
        mobs.spawn(LIGHTNING_BOLT, pos(0, 0, 0))
    }
})
gameplay.setWeather(RAIN)
```
