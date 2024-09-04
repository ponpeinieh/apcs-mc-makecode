### @hideIteration false 
### @flyoutOnly 1
### @explicitHints 1


# 狼驅趕(一)

## 步驟 1
將``||agent:Agent 道具設爲||``設置為**絆線鉤**並將數量設置為**64**。

## 步驟 2
使用``||loops:重複 判斷||``方塊，並在``||loops:重複 判斷||``方塊內放置條件。

#### ~ tutorialhint

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
})

``` 
## 步驟 3
在``||loops:重複 判斷||``方塊內添加``||agent:Agent 放置||``和``||agent:Agent 移動||``方塊。

```blocks
player.onChat("run", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
``` 