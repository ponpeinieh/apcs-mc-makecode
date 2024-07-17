### @explicitHints 1

# 單元 3: 第 3 課 - 種植一些花朵

## 步驟 1
將 ``||Player:on chat command||`` 程式碼方塊中 **run** 元素改名為 **plant_flowers**。

拖放 ``||Loops:repeat [4] times||`` 程式碼方塊到你的 ``||Player:on chat command||`` 方塊中，並設置數字為你公園一邊的方塊數。在我們的示例中，我們將這個數字設置為 **20**。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
    	
    }
})
```

## 步驟 2
現在將 ``||Agent:agent set active slot||`` 程式碼方塊拖放到 ``||loops:repeat loop||`` 內部。

#### ~ tutorialhint
``` blocks
player.onChat("plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(1)
    }
})
```

## 步驟 3
前往左側菜單中的新工具箱抽屜，名為 ``||Math:MATH||``。

這個抽屜中的方塊允許你在代碼中使用數學運算。

將 ``||Math:pick random [0] to [10]||`` 程式碼方塊拖放到你的 ``||Player:on chat command||`` 方塊中，並將其放置在 ``||Agent:agent set active slot||`` 的數字元素位置。

這意味著你的代理現在會隨機選擇一個庫存槽位，而不是特定選擇一個槽位。

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
編寫你的代理隨機移動。現在訪問 ``||Agent:Agent||`` 抽屜，將 ``||Agent:agent move [forward]||`` 程式碼方塊拖放到編碼工作區。

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
再次添加一個 ``||Math:pick random [0] to [10]||`` 來取代 ``||Agent:agent move [forward]||`` 中的數字橢圓形。

將 ``||Math:pick random [0] to [10]||`` 的第二個數字更改為 **20**。

當這行代碼被添加時，你的代理會向前移動到其當前位置和 20 個方塊之間的隨機位置。

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
將兩個 ``||Agent:agent place [forward]||`` 程式碼方塊拖放到編碼工作區，並使用下拉菜單將第二個方塊設置為 **back**。

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
再次拖放一個 ``||Agent:agent set active slot||`` 程式碼方塊到編碼工作區。

返回 ``||Math:MATH||`` 抽屜，並添加另一個 ``||Math:pick random [0] to [10]||``。將其添加到你的 ``||Agent:agent set active slot||`` 程式碼方塊中，並將數字更改為 1 和 5。

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
現在回到 ``||Agent:Agent||`` 抽屜，並選擇一個 ``||Agent:agent move [forward]||`` 程式碼方塊到編碼工作區，將其設置為 **back**。

選擇另一個 ``||Math:pick another pick random [0] to [10]||``，並將其添加到你的 ``||Agent:agent move [back]||`` 程式碼方塊中，並將數字設置為 **0** 和 **20**。

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
現在前往 ``||Agent:Agent||`` 抽屜，將兩個 ``||Agent:agent place [forward]||`` 程式碼方塊拖放到編碼工作區，並將第二個設置為 **back**。

最後，拖放一個 ``||Agent:agent move [left]||`` 程式碼方塊到編碼工作區，完成這段代碼。

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
將你的代理定位並運行代碼。將你的代理放在公園的一個角落，使代理的

背部靠著柵欄，公園的主體在左邊。

測試你的代碼。你的代理現在應該會向前移動到一個隨機位置，種植兩種隨機選擇的花朵，後退，再重複一次，然後向左移動，以此類推。這樣就可以創建一個隨機的花卉草地。