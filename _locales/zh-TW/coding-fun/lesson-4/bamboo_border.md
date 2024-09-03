### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 竹子邊界

## 步驟 1
我們為您準備了一段起始代碼。先嘗試運行它。最終目標是沿著熊貓的地塊的 **4** 個邊種植竹子。

```ghost
player.onChat("bamboo", function () {
    agent.setItem(BAMBOO, 64, 1)
    for (let index = 0; index < 16; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})
```