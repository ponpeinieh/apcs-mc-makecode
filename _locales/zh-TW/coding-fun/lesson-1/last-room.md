### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# 程式設計代理移動到金壓力板上！

## 步驟 1
程式設計代理到達金壓力板。您需要站在自己的金壓力板上，而代理需要站在另一個金壓力板上。完成後，按下 **播放** 按鈕來編譯程式碼。進入 Minecraft 運行您的程式碼。


```ghost
player.onChat("last", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```