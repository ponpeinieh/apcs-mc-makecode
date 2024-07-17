### @explicitHints 1

# 單元 3：課程 2 - 編碼水景

## 步驟 1
將 ``||Player:on chat command||`` 塊中的 **run** 元素重新命名為 **park_fountain**。

挖掘噴泉邊界。接下來的階段是創建噴泉的框架或邊界。我們將通過先挖掘地面，然後用 **Cobblestone** 方塊替換這些方塊來完成這一步。

## 步驟 2
將 ``||Loops:repeat [4] times||`` 代碼塊拖放到你的 ``||Player:on chat command||`` 中，並將其設置為 **4**。

這意味著我們的代理將重複執行接下來的四組動作。因為我們將使用多個循環，這第一個將被稱為 **外部** 循環。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {

    }
})
```

## 步驟 3
將另一個 ``||Loops:repeat [4] times||`` 代碼塊拖放到你的 ``||Player:on chat command||`` 中，並將其放在第一個循環內。

將一個 ``||Agent:agent destroy [down]||`` 代碼塊添加到編碼工作區中，並設置為使用下拉菜單設置為 **down**。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
        }
    }
})
```

## 步驟 4
將 ``||Agent:agent move [forward]||`` 代碼塊拖放到編碼工作區中，在上一步添加的 ``||Loops:repeat [4] times||`` 後放置。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
    }
})
```

## 步驟 5
將一個 ``||Agent:agent turn [left]||`` 代碼塊放在第一個或 **外部** ``||Loops:repeat [4] times||`` 內，但在第二個或 **內部** ``||Loops:repeat [4] times||`` 外。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(LEFT_TURN)
    }
})
```

## 步驟 6
現在測試你的代碼。你將看到你的代理挖出一個 5 x 5 的框架。

填充 Cobblestone。現在我們需要用 Cobblestone 填充這個新形成的洞，作為噴泉的框架。

## 步驟 7
將 ``||Agent:agent set active slot||`` 代碼塊拖放到 ``||Player:on chat command||`` 塊內的 ``||Loops:repeat [4] times||`` 下方。代理不需要重複執行這個，這是一個新動作的一部分。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(LEFT_TURN)
    }
    agent.setSlot(1)
})
```

## 步驟 8
現在重複這些步驟，將新的代碼集放在 ``||Agent:agent set active slot||`` 之後，僅將 ``||Agent:agent destroy [down]||`` 替換為 ``||Agent:agent place [down]||``。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
})
```

## 步驟 9
再次測試你的代碼。注意，這次代理會挖掘地面，然後用 **Cobblestone** 替換它。這形成了噴泉的框架。

在噴泉內部挖掘。現在，我們需要編寫代理以清理噴泉內部的地面，以防水淹過公園。

## 步驟 10
拖放一個 ``||Agent:agent move [left]||`` 代碼塊，將其更改為 **left**，並將其放在當前代碼的最後。

再獲取另一個 ``||Agent:agent move [forward]||`` 代碼塊，保持設置為 **forward**，並將其放在當前代碼的最後。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    agent.move(LEFT, 1)
    agent.move(FORWARD, 1)
})
```

## 步驟 11
將一個 ``||Loops:repeat [3] times||`` 代碼塊拖放到你的 ``||Player:on chat command||`` 代碼的末尾，並將其設置為 **3**。

在噴泉框架的中心有一個 3 x 3 的草塊，代理需要清理。因此，我們需要給它三個動作，並重複這三個動作三次。同樣，我們將第一個稱為外部循環，第二個稱為內部循環。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {

    }
})
```

## 步驟 12
再獲取一個 ``||Loops:repeat [3] times||`` 代碼塊。將其放在第一個循環內，並設置為 **3**。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 3; index++) {

        }
    }
})
```

## 步驟 13
接下來，讓你的代理 ``||Agent:agent destroy||``，並使用下拉菜單設置為 **down**。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 3; index++) {
            agent.destroy(DOWN)
        }
    }
})
```

## 步驟 14
讓你的代理 ``||Agent:agent move [forward]||``，並將其設置為 **1**。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 3; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
    }
})
```

## 步驟 15
讓你的代理回到位置。讓你的代理 ``||Agent:agent move [back]||``，並將其設置為 **3**。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 3; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.move(BACK, 3)
    }
})
```

## 步驟 16
讓你的代理 ``||Agent:agent move [left]||``。

這將使你的代理位於要移除的下一組三個塊的開始位置，外部循環將確保這個動作重複三次。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 3; index++) {
        for (let index = 0; index < 3; index++) {
            agent.destroy(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.move(BACK, 3)
        agent.move(LEFT, 1)
    }
})
```

## 步驟 17
測試你的代碼，觀察你的代理挖掘噴泉框架的內部。

## 步驟 18
編寫水特效。將一個 ``||Agent:agent move [forward]||`` 代碼塊拖放到你的主代碼中。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    agent.move(FORWARD, 1)
})
```

## 步驟 19
獲取一個 ``||Agent:agent move [forward]||`` 代碼塊，將 **forward** 更改為 **right**，並將數字更改為 **2**。這將使你的代理位於噴泉的中心。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    agent.move(RIGHT, 2)
})
```

## 步驟 20
獲取一個 ``||Loops:repeat [5] times||`` 代碼塊，將數字更改為 **5**。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 5; index++) {

    }
})
```

## 步驟 21
返回到 ``||Agent:AGENT||`` 抽屜，獲取一個 ``||Agent:agent place [down]||`` 代碼塊，並將其添加到你的代碼中，在 ``||Loops:repeat [5] times||`` 塊內部。
這意味著你的代理將在噴泉底部放置五塊 **Cobblestone** 中的第一塊。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    for (let index = 0; index < 5; index++) {
        agent.place(DOWN)
    }
})
```

## 步驟 22
獲取一個 ``||Agent:agent move [forward]||`` 代碼塊，將其添加到你的代碼中，並將其更改為 **up**。

這將使你的代理位於噴泉的頂部，準備添加水。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    agent.move(UP, 1)
})
```

## 步驟 23
獲取一個 ``||Agent:agent set active slot||`` 代碼塊，將其添加到你的代碼中，並將其設置為 **2**，這是你的代理庫存中具有 **Bucket of Water** 的槽位，然後添加一個 ``||agent:agent place||`` **down** 塊。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    // 前面的代碼不重複列出
    agent.setSlot(2)
    agent.place(DOWN)
})
```

## 步驟 24
現在在將噴泉放置在公園的某個地方之前，檢查並測試你的代碼。