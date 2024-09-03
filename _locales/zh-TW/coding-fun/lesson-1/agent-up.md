### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# 程式設計代理移動到金壓力板上！

## 步驟 1
使用 ``||player:玩家 在聊天指令為||`` 和 ``||agent:Agent 移動 [前]||`` 命令來程式設計代理移動到金壓力板。您可以程式設計代理向**上**移動。完成後，按下 **播放** 按鈕來編譯程式碼。進入 Minecraft 遊戲中運行您的程式碼。



```ghost
player.onChat("up", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```