### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 建造市政廳！

## 步驟 1
我們為你創建了一個 **plantSeed** 函數。這個函數就是你在之前活動中使用的代碼。現在將 ``||player: 在聊天指令為||`` 命令拖到工作區，並命名為 **run**。添加一個 ``||loops: 重複||`` 迴圈，點擊 **進階** 部分，然後點擊 **函數**，將 ``||function: 呼叫 plantSeed||`` 函數拖到你的迴圈中。計算 Agent 需要重複 **plantSeed** 函數的次數。

### ~ 教學提示
函數位於 **進階** 部分。為代碼添加註解也是一個好習慣，就像我們為你留的有關函數的註解一樣。

```template
/**
 * 一個函數允許你輕鬆重複使用代碼。
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    agent.place(DOWN)
}
```

```ghost
player.onChat("plantSection", function () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
})
```
