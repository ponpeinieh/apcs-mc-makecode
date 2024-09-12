### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1

# 漂亮的圖案！

## 步驟 1
你的任務是在浴池的地板邊界上構建一個**石英方塊**和**青金石方塊**的交替圖案。首先，創建兩個變數：``||variable:變數 blockA||`` 和 ``||variable:變數 blockB||``。將 ``||variable:變數 blockA||`` 設置為**石英方塊**，將 ``||variable:變數 blockB||`` 設置為**青金石方塊(Block of Lapis Lazuli)**。將這些命令添加到``||player:當聊天指令||``內。

## 步驟 2
在 ``||logic: 如果 那麽||`` 語句中，檢查``||variable:變數 count||``是否等於 **0**。如果為真，Agent 需要放置來自``||variable:變數 blockA||``的方塊（它應在第一個物品欄槽中），然後``||agent:Agent 破壞 [下方]||``，``||agent:Agent 放置 [下方]||``，並``||variable:變數 count 改變 1||``。否則，Agent 應該放置來自``||variable:變數 blockB||``的方塊（也在第一個物品欄槽中），然後放置這些方塊，並``||variable:變數 count 改變 -1||``。在``||logic: 否則||``塊之後，讓代理``||Agent:Agent 移動 [前]||``  **1**格。

## 步驟 3
Agent 需要在``||Loops:重複 判斷||``迴圈中重複步驟2的放置方塊過程。迴圈應在``||Agent:agent 偵測 方塊||`` **前方** 的條件為假的情況下繼續運行。

## 步驟 4
前面的步驟涵蓋了在水池的一側放置方塊的過程。由於水池有**4**個側面，添加一個``||Loops:重複 [4] 次||``迴圈。在這個迴圈內，將``||variable:變數 count||``重置為**0**，然後重複前面步驟中的邏輯。在完成每一側後，使用``||Agent:Agent 轉動 [右]||``讓 Agent 轉向並繼續沿著下一個側面逆時針方向構建。


```template
let count = 0
player.onChat("floor", function () {
    count = 0
})
```


```ghost
player.onChat("floor", function () {
    count = 0
    for (let index = 0; index < 4; index++) {
        while (!(agent.detect(AgentDetection.Block, FORWARD))) {
            if (count == 0) {
                agent.setItem(blockA, 1, 1)
                agent.destroy(DOWN)
                agent.place(DOWN)
                count += 1
            } else {
                agent.setItem(blockB, 1, 1)
                agent.destroy(DOWN)
                agent.place(DOWN)
                count += -1
            }
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})
let count = 0
let blockB = 0
let blockA = 0
blockA = BLOCK_OF_QUARTZ
blockB = LAPIS_LAZULI_BLOCK
```
