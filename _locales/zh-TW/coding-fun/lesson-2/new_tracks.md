### @hideIteration false 
### @flyoutOnly 1
### @explicitHints 1


# 編程代理沿著海龜足跡移動！

## 第一步
使用 ``||agent:Agent 移動 [前]||`` 積木來讓代理沿著海龜足跡移動。

#### ~ tutorialhint 
嘗試使用 ``||loops:重複||`` 積木來使代碼更有效率。

## 第二步
完成後，按下 **播放** 按鈕來編譯代碼。不要忘了在 Minecraft 中運行你的代碼。

```blocks
player.onChat("run", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
```