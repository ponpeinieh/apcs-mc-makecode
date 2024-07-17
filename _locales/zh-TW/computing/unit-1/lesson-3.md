### @hideIteration true 
### @explicitHints true


# 課程三

## 步驟一
結合你到目前為止所學到的一切，你能編寫你的代理在水上建一座橋嗎？
這個間隙有3個方塊寬。
完成後，按下**綠色三角按鈕**來編譯程式碼，然後進入麥塊，按**T**鍵並輸入**build_a_bridge**。

### ~ tutorialhint
記得在放置方塊時要**向下**放置！
請先確認你的代理的物品庫中有**建築材料方塊**。方塊要在**第一個槽**中。

```ghost
player.onChat("run", function () {
    player.say(":)")
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.place(FORWARD)
    agent.destroy(FORWARD)
    agent.collectAll()
})
``` 

