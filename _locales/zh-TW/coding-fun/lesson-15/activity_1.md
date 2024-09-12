### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1

# 採礦石英！

## 步驟 1
編寫一些代碼來**計算**你需要多少**方塊**來建造剩下的柱子。以下是一些數據：總共有**6根柱子**，每根柱子**6個方塊高**。首先在``||loops: 當啓動時||``創建並設置``||variable:height(高度)||``和``||variable:quantity(數量)||``變數為正確的數值，然後創建一個``||variable:total blocks(總方塊數)||``變數。

## 步驟 2
設置一個條件，``||logic: 如果 那麽||``，``||variable:total blocks(總方塊數)||`` = ``||variable:height(高度)||`` * ``||variable:quantity(數量)||``，然後``||player: 玩家 説出||`` "收集到足夠的方塊！"。

## 步驟 3
現在添加一個``||variable: 變數 total blocks(總方塊數) 改變 1||`` 的命令和``||player: 玩家 説出||`` ``||variable:total blocks(總方塊數)||``，這樣你就可以知道你收集了多少方塊。確保添加``||blocks:方塊 在被破壞的方塊為 柱狀石英方塊 時||``之中，這樣在破壞方塊時你會看到數量變化。當你完成後，你會看到消息 "收集到足夠的方塊！"。


```ghost
blocks.onBlockBroken(PILLAR_QUARTZ_BLOCK, function () {
    total_blocks += 1
    if (total_blocks == height * quantity) {
        player.say("收集到足夠的方塊！")
    }
})
let total_blocks = 0
let quantity = 0
let height = 0
height = 6
quantity = 6
```
