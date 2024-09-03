### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 確保區域安全

## 步驟 1
編程代理建造**橡木圍欄**。代理需要將**橡木圍欄**方塊放置在右側，破壞障礙物並向前移動。圍欄應該是**17個方塊**長。

#### ~ tutorialhint
確保代理在右側放置方塊，在左側破壞方塊。

```blocks
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
            }
})
```
```ghost
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
        agent.place(RIGHT)
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    }
})
``` 

