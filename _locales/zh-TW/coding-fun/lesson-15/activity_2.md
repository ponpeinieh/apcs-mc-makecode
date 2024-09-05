### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1

# 柱子！

## 步驟 1
現在來建造輸水道！首先，創建``||variable:長度(length)||``和``||variable:段數(segments)||``變數。然後在``||loops:當啓動時||``將``||variable:長度(length)||``設置為**5**，將``||variable:段數(segments)||``設置為**6**。

## 步驟 2
現在，在``||player:當聊天指令||``內，你需要添加代理(Agent)建造**1**個部分所需的所有動作：``||Agent:agent 道具設爲 柱狀石英||``64個，``||agent:放置||``和``||agent:向前移動||``。Minecraft中的水會隨著坡度流動，因此代理(Agent)需要**向左、向右和向下放置**方塊。將這些動作全部放置在一個``||loops:重複||``循環中，該循環將重複``||variable:長度(length)||``次。

## 步驟 3
現在將第一個``||loops:重複||``循環嵌套在另一個重複``||variable:段數(segments)||``次的``||loops:重複||``循環中。試試看在Minecraft中運行吧！

### ~ tutorialHint
在內部循環之前添加``||agent:代理向下移動||``方塊，這樣才能讓代碼正常工作！


```ghost
player.onChat("build", function () {
    agent.move(DOWN, 1)
    for (let index = 0; index < Segments; index++) {
        for (let index = 0; index < length; index++) {
            agent.setItem(WHITE_CONCRETE, 64, 1)
            agent.place(LEFT)
            agent.place(RIGHT)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.move(DOWN, 1)
    }
})
let Segments = 0
let length = 0
length = 5
Segments = 6
```
