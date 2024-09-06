### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 驅趕

## 步驟 1
代理需要設置**絆線鉤**來防止狼進入。將``||agent:Agent 道具設爲||``設置為**絆線鉤**並將數量設置為**64**。使用``||loops:重複 判斷||``方塊，並在其中放置條件。

#### ~ tutorialhint
記得在你的條件中使用**不成立**。

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
})

``` 
```ghost
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
``` 