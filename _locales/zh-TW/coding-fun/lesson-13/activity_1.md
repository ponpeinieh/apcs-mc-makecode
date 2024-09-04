### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 熔岩游泳

## 步驟 1
你的挑戰是 ``||player:游泳||`` 穿越熔岩湖。嘗試對 **最近的玩家** ``||mobs:生物 套用效果 抗火||``。


```ghost
player.onTravelled(SWIM_LAVA, function () {
    mobs.applyEffect(FIRE_RESISTANCE, mobs.target(NEAREST_PLAYER), 10, 1)
    mobs.clearEffect(mobs.target(NEAREST_PLAYER))
})
```
