### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 牛

## 步驟 1
查看初始代碼並嘗試執行它。此代碼允許你在不數方塊的情況下導航代理(Agent)。觀察代理需要走的路徑，並確保你用正確的轉向來完成編碼序列，使代理能夠到達**金壓力板**。

```template
player.onChat("sheep", function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})
```