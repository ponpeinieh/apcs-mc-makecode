### @explicitHints 1

# 單元 3: 課程 3 - 種植一些花朵

## 步驟 1
將 ``||player:玩家 在聊天指令為||`` 代碼方塊中 **run** 名稱改名為 **plant_flowers**。

拖放 ``||Loops:重複 [4] 次||`` 代碼方塊到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，並將次數設為公園一邊的方塊數。在我們的代碼範例中，我們將這個數字設置為 **20**。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
    	
    }
})
```

## 步驟 2
現在將 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊拖放到 ``||Loops:重複 [20] 次||`` 內部。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(1)
    }
})
```

## 步驟 3
前往左側的新的工具箱抽屜，名為 ``||Math:數學||``。

這個抽屜中的代碼方塊允許你在代碼中使用數學運算。

將 ``||Math:pick random [0] to [10]||``**(隨機選取0-10的整數)**代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，並將其放置在 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 的數字位置。

這意味著你的代理現在會隨機選擇一個庫存槽位，而不是選擇一個固定的槽位。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(0, 10))
    }
})
```

## 步驟 4
將第一個數字設置為 **1**，第二個數字設置為 **5**，對應於代理庫存中的五個槽位。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```

## 步驟 5
接著讓你的代理隨機移動。將 ``||agent:Agent 移動 [前]||`` 代碼方塊拖放到編碼工作區。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, 1)
    }
})
```

## 步驟 6
再次添加一個 ``||Math:pick random [0] to [10]||`` 來取代 ``||agent:Agent 移動 [前]||`` 中的數字。

將 ``||Math:pick random [0] to [10]||`` 的第二個數字更改為 **20**。

這行代碼會讓你的代理向前移動, 到達當前位置和前方**20**個方塊之間的隨機位置。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
    }
})
```

## 步驟 7
將兩個 ``||Agent:Agent 放置 [前]||`` 代碼方塊拖放到編碼工作區，並將第二個代碼方塊的方向設為 **後**方。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
    }
})
```

## 步驟 8
再次拖放一個 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊到編碼工作區。

返回 ``||Math:數學||`` 抽屜，並添加另一個 ``||Math:pick random [0] to [10]||``。將其添加到你的 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊中，並將數字更改為 1 和 5。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```

## 步驟 9
放置一個 ``||agent:Agent 移動 [前]||`` 代碼方塊到編碼工作區，將其方向設為 **後**方。

選擇另一個 ``||Math:pick random [0] to [10]||``，並將其添加到你的 ``||Agent:agent move [back]||`` 代碼方塊中，並將數字設置為 **0** 和 **20**。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
    }
})
```

## 步驟 10
再將兩個 ``||Agent:Agent 放置 [前]||`` 代碼方塊拖放到編碼工作區，並將第二個方向設為**後**方。

最後，拖放一個 ``||agent:Agent 移動 [左]||`` 代碼方塊到編碼工作區。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.move(LEFT, 1)
    }
})
```

## 步驟 11
最後，將你的代理定位並運行代碼。將你的代理移動到公園的一個左下方角落，使代理的背對著柵欄，公園的主體在左邊。

測試你的代碼。你的代理現在應該會向前移動到一個隨機位置，種植兩種隨機選擇的花朵，然後往後倒退，再重複一次，然後向左移動，以此類推。這樣就可以創建一個隨機的花卉草地。