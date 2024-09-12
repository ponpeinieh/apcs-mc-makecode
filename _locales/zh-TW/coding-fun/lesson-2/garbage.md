### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# 編程代理收集所有垃圾！

## 第一步
使用代理清除海龜足跡上的垃圾，可以使用 ``||agent:Agent 破壞||`` 和 ``||agent:Agent 收集所有||`` 這些積木。嘗試使用 ``||loops:重複 執行||`` 積木來使代碼更加高效。完成後，按下 **播放** 按鈕來編譯代碼。不要忘了在 Minecraft 中運行你的代碼。

```ghost
player.onChat("garbage", function () {
    for (let index = 0; index < 4; index++) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
})
```