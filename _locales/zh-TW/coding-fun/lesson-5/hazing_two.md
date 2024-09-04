### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @flyoutOnly 1
### @explicitHints 1


# 狼驅趕(二)

## 步驟 1
步驟1是執行「狼驅趕(二)」挑戰。

## 步驟 2
完成後，按下**播放**按鈕來編譯代碼。別忘了在Minecraft中運行你的代碼。

```blocks
player.onChat("run", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})
```
