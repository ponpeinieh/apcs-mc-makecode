https://minecraft.makecode.com/#tutorial:73734-89839-36612-86062

# Unit 2 Lesson 1 : Code a Road Network 單元二 課程一 : 編程馬路

```blocks
player.onChat("run", function () {})
blocks.fill(GRASS, world(0, 0, 0), world(0, 0, 0),FillOperation.Replace)
agent.teleportToPlayer()
agent.move(FORWARD, 1)
agent.turn(LEFT_TURN)
agent.destroy(FORWARD)
agent.place(FORWARD)
agent.collectAll()
```

## Step 1 步驟一

Rename the **run** element of the ``||player:on chat command||`` block to **road_1**. Select the ``||blocks: fill with||`` code block and drag it into your ``||player:on chat command||`` block.

將``||player:玩家 在聊天指令為||``方塊的 **run** 重新命名為 **road_1**。選擇``||blocks:方塊 填充||``代碼塊並將其拖曳到你的``||player:玩家 在聊天指令為||``方塊中。

```blocks
player.onChat("road_1", function () {
	blocks.fill(GRASS, pos(0, 0, 0), pos(0, 0, 0),FillOperation.Replace)
})
```

## Step 2 步驟二

Use the drop-down menu to change the type of block from **Grass** to **Gray Concrete**.

使用下拉選單將方塊類型從**草地**更改為**灰色混凝土**。

```blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 3 步驟三

Now open ``||positions:POSITIONS||``  toolbox drawer and drag the ``||positions:world [0] [0] [0]||`` code block onto your coding Workspace.
Drag the ``||positions:world [0] [0] [0]||`` block and replace the ``||positions:relative||`` positions block inside the ``||blocks:fill with||`` block.

現在打開``||positions:坐標||``工具箱抽屜，將``||positions:世界 [0] [0] [0]||``代碼塊拖到你的編程工作區。
將``||positions:世界 [0] [0] [0]||``代碼塊拖曳並替換``||blocks:方塊 填充||``方塊中的``||positions: 相對||``位置方塊。

```blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 4 步驟四

Drag another ``||positions:world [0] [0] [0]||`` positions code block from the ``||positions:POSITIONS||`` drawer and replace the second  ``||positions:relative||`` positions block inside the ``||blocks:fill with||`` block.

從``||positions:坐標||``工具箱抽屜中再拖一個``||positions:世界 [0] [0] [0]||``位置代碼塊，並替換``||blocks:方塊 填充||``方塊中的第二個``||positions:相對||位置方塊。


```blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## Step 5 步驟五

We are almost ready to test our code, however there is one more important thing we have to do to make this code work properly. Change the center, or **Y** coordinate, to one number lower. In this example, this will be **68**. Now test your code. If you have coded correctly, you should see a road appear in place of the Grass.

我們快要準備好測試我們的代碼了，不過還有一件重要的事情需要做以使這段代碼正常運行。將第二個位置參數，即**Y**坐標，減少1。在這個例子中，這將是**68**。現在測試你的代碼。如果你編碼正確，應該會看到一條路出現在草地上。

```blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -565),
    world(61,68,-569),
    FillOperation.Replace
    )
})
```

## Step 6 步驟六

Repeat the steps for the second road.
重複以上的步驟完成第二條馬路。



```blocks
player.onChat("road_2", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -532),
    world(61,68,-536),
    FillOperation.Replace
    )
})
```

## Step 7 步驟七

**(Extension)** With two roads done, build more using the code you have just created. When you are finished, go to the **Unit 2 Lesson 1 NPC** and ask for some **carpet** to make road markings with using your agent to place them.

**(延申)** 使用剛剛創建的代碼建造更多道路。完成後，去到**單元二課程一的NPC**(非玩家控制角色，Non-Player Character)並要求一些**地毯**，讓代理使用它們放置道路標線。



