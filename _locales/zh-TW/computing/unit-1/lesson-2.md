### @hideIteration false 
### @explicitHints 1


# 單元一 : 課程二

## 步驟一
要編程讓您的代理移動，請選擇``||player:玩家 在聊天指令為||``指令，並將其名稱從**run**更改為**move**。選擇``||agent:Agent 移動||``命令並將其拖動到``||player:玩家 在聊天指令為||``指令內。

### ~ tutorialhint
不要忘記更改你希望代理移動的步數距離。

## 步驟二
確保在最終程式碼中結合``||agent:Agent 移動||``和``||agent:agent 轉動||``指令。確保你的代理跟隨橘色線。

## 步驟三
完成後，按下**綠色三角按鈕**來編譯程式碼，然後進入麥塊，按**T**鍵並輸入**move**。

## 步驟四
要編寫你的代理砍樹的程式碼，請選擇一個新的``||player:玩家 在聊天指令為||``指令。現在你需要添加``||agent:Agent 移動||``和``||agent:Agent 破壞||``指令。想一想你希望代理朝哪個方向移動。

### ~ tutorialhint
代理可以**向上、向下、向前、向後、向左或向右**移動。

## 步驟五
不要忘記在程式碼中添加``||agent:Agent 收集全部||``指令，以確保代理收集所有木板方塊。

## 步驟六
現在你可以練習將這些指令以不同的組合來使用。

```ghost
player.onChat("run", function () {
    player.say(":)")
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.destroy(FORWARD)
    agent.collectAll()
})
``` 
