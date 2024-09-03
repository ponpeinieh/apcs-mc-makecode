### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 尋找小熊！

## 步驟 1
程式設置代理挖掘一條不知道多遠的路徑，使用 ``||Loops:重複 判斷||`` 和 ``||Agent:agent 偵查 方塊||`` 命令。代理需要 ``||Agent:Agent 破壞 [前] 和 [上]||``，讓你能夠穿過所有的雪！完成後，按下 **Play** 按鈕來編譯代碼。不要忘記在 Minecraft 中執行你的代碼。

#### ~ tutorialhint 
查看代碼片段的形狀當你將它們拼接在一起時。使用 ``||agent:Agent 移動 [前]||``。

```template
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
    	
    }
})
```

```ghost
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})
``` 