### @explicitHints 1

# 單元 2：課程 2 - 編碼建築

## 步驟 1
讓我們從建造牆壁開始。將``||player:玩家 在聊天指令為||``方塊中的 **run** 名稱重新命名為 **build_a_structure**。將``||Agent:Agent 將物品槽 [1] 設爲使用中||``方塊拖放到編碼工作區，並將其添加到``||player:玩家 在聊天指令為||``方塊中。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
})
```

## 步驟 2
將``||Agent:Agent 能力 [移動時放置(place on move)]||``方塊拖到``||player:玩家 在聊天指令為||``中。將此方塊的啓用狀態從 **關** 改為 **開**。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
})
```

## 步驟 3
現在讓我們給代理一些建造指令。從左側``||Loops:迴圈||``工具箱抽屜，將``||Loops:重複 [4] 次||``方塊拖到``||player:玩家 在聊天指令為||``中, 準備做下一步。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
    	
    }
})
```

## 步驟 4
從``||Agent:代理||``工具箱抽屜，拖動``||agent:Agent 移動 [前]||``，將其放置在``||Loops:重複 [4] 次||``中。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 1)
    }
})
```

## 步驟 5
將``||agent:Agent 移動 [前]||``方塊中的距離更改為 **5**。拖動``||agent:Agent 轉動 [左]||``，將其放置在``||Loops:重複 [4] 次||``中。您可以根據建造的內容和位置更改方向，這個例子，我們保留**左**的方向。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
})
```

## 步驟 6
測試代碼，它將構建四面牆並使代理再次接近起點，但是留下了一個缺口。

## 步驟 7
返回``||Agent:代理||``工具箱抽屜，添加另一個``||agent:Agent 移動 [前]||``，然後將其更改為 **上**。但這次將此方塊放置在``||Loops:重複 [4] 次||``方塊之外。這將使您的代理向上移動一格，並在其移動時填充下面的方塊。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
})
```

## 步驟 8
添加另一個``||Agent:Agent 能力 [移動時放置(place on move)]||``，並將其啓用設置為 **關**。因為我們不希望代理在移動時放置方塊。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
})
```

## 步驟 9
添加另一個``||agent:Agent 移動 [前]||``，然後將其更改為 **右**。這將使您的代理回到原本開始位置的上一層，準備開始建構第二層牆壁。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(RIGHT, 1)
})
```

## 步驟 10
現在，我們需要重複這個過程，建造四層墻壁。這需要另一個迴圈。返回``||Loops:迴圈||``抽屜，將另一個``||Loops:重複 [4] 次||``帶到您的編碼工作區，但這次，我們所要重複的工作是剛剛完成的建構一層牆壁的步驟。

## 步驟 11
返回``||Agent:代理||``工具箱抽屜，添加另一個``||Agent:Agent 能力 [移動時放置(place on move)]||``，並將啓用設置為 **開**。測試您的代碼。

## 步驟 12
我們接著建構屋頂。從``||Agent:代理||``工具箱抽屜，添加另一個``||Agent:Agent 將物品槽 [1] 設爲使用中||``，但設置為 **2**(使用 **石頭半磚**)。使用另一個迴圈，使代理前進 5 格，然後左移。然後讓代理後退 5 格，再次左移。然後重複 3 次。

### ~ tutorialhint

``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
})
```

## 步驟 13
接著我們開始建造窗戶和門。添加另一個``||Agent:Agent 能力 [移動時放置(place on move)]||``，並將其啓用設置為 **關**(這樣它就不會放置任何屋頂瓦片)。然後添加另一個``||agent:Agent 移動 [前]||``，並設置為 **下** 和 **3**。這將使您的代理向下移動三格，到達窗戶放置的水平位置。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
})
```

## 步驟 14
添加另一個``||agent:Agent 移動 [前]||``，保持方向為``||Agent:前||``及距離**1**。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
})
```

## 步驟 15
添加另一個``||Agent:Agent 將物品槽 [1] 設爲使用中||``，並將其設置為 **3**。這將選擇代理的第三個庫存槽，也就是使用 **玻璃窗格** 成為下一個建築材料。

添加``||agent:Agent 破壞 [前]||``方塊。將其放置在最後一個方塊下方，並將其值更改為 **右**。這將使您的代理在牆壁上向右移除一個方塊，做為放置窗戶的地方。

## 步驟 16
現在選擇``||Agent:Agent 放置 [前]||``方塊，並將方向改為 **右**。這將使您的代理在剛剛破壞的牆壁方塊空隙中放置一個**玻璃窗格**。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
})
```

## 步驟 17
添加另一個``||agent:Agent 移動 [前]||``方塊。維持方向為**前** 但將距離更改為 **2**。

## 步驟 18
由於我們接著要安裝大門，我們需要在牆上破壞兩個格子高的方塊。首先，放置一個``||agent:Agent 破壞 [前]||``方塊並將其設置為 **右** 來破壞第一個方塊。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
})
```

## 步驟 19
添加另一個``||agent:Agent 移動 [前]||``方塊。將其更改為 **下**。這將使您的代理移動到我們要安裝門的位置。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
})
```

## 步驟 20
添加另一個``||agent:Agent 破壞 [前]||``方塊。將其更改為 **右**。

返回``||Agent:代理||``抽屜，並添加另一個``||Agent:Agent 將物品槽 [1] 設爲使用中||``方塊。將其更改為 **4**。這將選擇您的代理的第四個庫存槽，即 **相思木門**。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
})
```

## 步驟 21
返回``||Agent:代理||``工具箱抽屜，並添加另一個``||Agent:Agent 放置 [前]||``方塊，將其更改為 **右**。這將放置您的木門並完成整個建築。測試您的代碼！

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
    agent.place(RIGHT)
})
```