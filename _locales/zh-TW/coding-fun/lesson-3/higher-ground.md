### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1


# 高地！

## 步驟 1
程式設置代理以建立一座高 **10** 塊的 **橡木** 塔。首先，確保代理擁有 **64** 塊 **橡木板**，使用 ``||Agent:agent 道具設爲 ||`` 命令。程式設置代理放置橡木板 **前方**、**左方** 和 **右方**，使用 ``||agent:Agent 放置 [前]||`` 區塊。在放置這些方塊後，代理需要 **向上移動**。

#### ~ tutorialhint 
試著使用 ``||Loops:重複 [10] 次||`` 區塊。

## 步驟 2
程式設置代理從塔上 **向下移動** 並構建 **梯子**，高度為 **10** 塊。你需要梯子才能爬上去！

#### ~ tutorialhint 
不要忘記在代理的庫存中選擇 **64** 塊 **梯子**，使用 ``||Agent:agent 道具設爲 ||``，以便代理能夠放置梯子。 


```ghost
player.onChat("tower", function () {
    agent.move(FORWARD, 1)
    agent.setItem(LADDER, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.move(UP, 1)
    }
    agent.move(DOWN, 10)
})
```