### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 躲過恐龍！

## 步驟 1
你需要通過讓自己 ``||mobs:隱形||`` 來 ``||player:偷偷溜過(潛行)||`` 恐龍。你能做到嗎？

### ~ tutorialHint
試試按下 Shift 和 W 鍵在 Minecraft 中偷偷溜過(潛行)。


```ghost
player.onTravelled(SNEAK, function () {
    mobs.applyEffect(INVISIBILITY, mobs.target(NEAREST_PLAYER), 3, 1)
})
```
