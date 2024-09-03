### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# 程式設計代理人沿著海龜軌道移動！

## 步驟 1
使用 ``||agent:Agent 移動 [前]||`` 積木將代理人沿著海龜軌道移動到大門。完成後，按下 **播放** 按鈕來編譯程式碼。不要忘記在 Minecraft 中運行您的程式碼。

```ghost
player.onChat("tracks", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
```