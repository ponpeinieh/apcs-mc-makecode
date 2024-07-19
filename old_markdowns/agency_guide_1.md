https://minecraft.makecode.com/#tutorial:27288-42319-90590-76278

# Unit 1 Lesson 2 單元一 課程二

```blocks
player.onChat("run", function () {})
player.say(":)")
agent.teleportToPlayer()
agent.move(FORWARD, 1)
agent.turn(LEFT_TURN)
agent.destroy(FORWARD)
agent.collectAll()
```

## Step 1 步驟一 @showhint 

To program your Agent to move, select an ``||player:on chat||`` command and rename it from **run** to **move**. Select an ``||agent: agent move||`` command and drag it inside the ``||player:on chat||`` command.

要編程讓您的代理移動，請選擇``||player:玩家 在聊天指令為||``指令，並將其名稱從**run**更改為**move**。選擇``||agent:Agent 移動||``命令並將其拖動到``||player:玩家 在聊天指令為||``指令內。

```
```
Don't forget to change the number of steps that you want the Agent to make.

不要忘記更改你希望代理移動的步數距離。

## Step 2 步驟 2

Make sure you combine ``||agent: agent move||`` and ``||agent:agent turn||`` commands for your final code. Make sure your Agent follows the orange line.

確保在最終程式碼中結合``||agent:Agent 移動||``和``||agent:agent 轉動||``指令。確保你的代理跟隨橘色線。

## Step 3 步驟 3

When done, press the **green triangle button** to compile the code, then go to Minecraft, press **T** and type **move**.

完成後，按下**綠色三角按鈕**來編譯程式碼，然後進入麥塊，按**T**鍵並輸入**move**。

## Step 4 步驟 4

To code your Agent to chop down a tree, select a new ``||player:on chat||`` command. Now you need to add ``||agent: agent move||``, ``||agent: agent destroy||`` commands. Think which direction you want the Agent to move.

要編寫你的代理砍樹的程式碼，請選擇一個新的``||player:玩家 在聊天指令為||``指令。現在你需要添加``||agent:Agent 移動||``和``||agent:Agent 破壞||``指令。想一想你希望代理朝哪個方向移動。

```
```
The Agent can move **up, down, forward, back, left or right**.

代理可以**向上、向下、向前、向後、向左或向右**移動。

## Step 5 步驟 5

Don't forget to add ``||agent: agent collect all||`` command to your code to make sure that the Agent collects all the plank blocks.

不要忘記在程式碼中添加``||agent:Agent 收集全部||``指令，以確保代理收集所有木板方塊。

## Step 6 步驟 6

Now you can practice using these commands in different combinations.

現在你可以練習將這些指令以不同的組合來使用。
