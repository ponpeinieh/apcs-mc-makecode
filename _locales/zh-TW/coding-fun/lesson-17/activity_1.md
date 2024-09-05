### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 種植種子！

## 步驟 1
首先，與代理互動以打開其物品庫並給予它種子。接著創建 ``||player: 在聊天指令為||`` 命令，並添加 ``||agent: 耕種 [前]||`` 和 ``||agent: 放置 [前]||``。

```ghost
player.onChat("plantSeed", function () {
    agent.till(FORWARD)
    agent.place(FORWARD)
})
```
