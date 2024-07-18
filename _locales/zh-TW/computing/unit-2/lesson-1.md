### @explicitHints 1

# 單元二 : 課程一 - 編程馬路

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

## 步驟一
將``||player:玩家 在聊天指令為||``代碼方塊的 **run** 重新命名為 **road_1**。選擇``||blocks:方塊 填充||``代碼方塊並將其拖曳到你的``||player:玩家 在聊天指令為||``代碼方塊中。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRASS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟二
使用下拉選單將方塊類型從**草地**更改為**灰色混凝土**。

### ~ tutorialhint

``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟三
現在打開``||positions:座標||``工具箱抽屜，將``||positions:世界 [0] [0] [0]||``代碼方塊拖到你的編程工作區。
將``||positions:世界 [0] [0] [0]||``代碼方塊拖曳並替換``||blocks:方塊 填充||``代碼方塊中的``||positions: 相對||``位置代碼方塊。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟四
從``||positions:座標||``工具箱抽屜中再拖一個``||positions:世界 [0] [0] [0]||``代碼方塊，並替換``||blocks:方塊 填充||``代碼方塊中的第二個``||positions:相對||``代碼方塊。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## 步驟五
我們快要準備好測試我們的代碼了，不過還有一件重要的事情需要做以使這段代碼正常運行。將第二個位置參數，即**Y**座標，減少1。在這個例子中，這將是**68**。現在測試你的代碼。如果你編碼正確，應該會看到一條路出現在草地上。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -565),
    world(61, 68, -569),
    FillOperation.Replace
    )
})

```

## 步驟六
重複以上的步驟完成第二條馬路。

### ~ tutorialhint
``` blocks
player.onChat("road_2", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -532),
    world(61, 68, -536),
    FillOperation.Replace
    )
})
```

## 步驟七
**(延申)** 使用剛剛創建的代碼建造更多道路。完成後，去到**單元二課程一的NPC**(非玩家控制角色，Non-Player Character)並要求一些**地毯**，讓代理使用它們放置道路標線。
