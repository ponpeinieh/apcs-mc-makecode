### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1


# 程式設計代理移動到金壓力板！

## 步驟 1
選擇一個 ``||player:玩家 在聊天指令為||`` 命令，並將其名稱從 **run** 改為 **1**。選擇一個 ``||agent:Agent 移動 [前]||`` 方塊並將其拖入 ``||player:玩家 在聊天指令為||`` 命令中。將代理移動的步數更改為 **3**，這樣代理就能到達金壓力板。完成後，按下 **播放** 按鈕來編譯程式碼，然後進入 Minecraft，按 **t** 並輸入 **1**。

#### ~ tutorialhint 
您可以通過更改 ``||agent:Agent 移動||`` 方塊內的數字來更改代理將移動的步數。您也可以使用 ``||agent:Agent 轉動||`` 方塊讓代理向左或向右轉動。



```ghost
player.onChat("1", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```