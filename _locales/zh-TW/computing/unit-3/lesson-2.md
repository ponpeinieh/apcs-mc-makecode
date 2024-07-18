### @explicitHints 1

# 單元 3：課程 2 - 編碼水景

## 步驟 1
將 ``||player:玩家 在聊天指令為||`` 代碼方塊中的 **run** 名稱重新命名為 **park_fountain**。

我們將建構一座噴泉。首先是創建噴泉的框架或邊界。我們將先挖掘地面，然後放置 **鵝卵石** 方塊。

## 步驟 2
將 ``||Loops:重複 [4] 次||`` 代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，並將次數設為 **4**。

這意味著我們的代理將重複執行接下來的動作四次。因為我們將使用多個迴圈，這第一個迴圈將被稱為 **外部** 迴圈。

### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {

    }
})
```

## 步驟 3
將另一個 ``||Loops:重複 [4] 次||`` 代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊中，並將其放在第一個迴圈內。這第二個迴圈將被稱為 **内部** 迴圈。

將一個 ``||agent:Agent 破壞 [下]||`` 代碼方塊添加到編碼工作區中，並將方向設置為 **下**。

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
將 ``||agent:Agent 移動 [前]||`` 代碼方塊拖放到編碼工作區中，然後放在``||agent:Agent 破壞 [下]||`` 代碼方塊之後。

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
將一個 ``||agent:Agent 轉動 [左]||`` 代碼方塊放在**外部**迴圈內，但在**內部**迴圈外。

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
現在測試你的代碼。你將看到你的代理挖出一個 5 x 5 的溝槽。

接著我們將填充**鵝卵石**。我們需要用**鵝卵石**填充這個新形成的溝槽，作為噴泉的底座框架。

## 步驟 7
將 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊拖放到 ``||player:玩家 在聊天指令為||`` 代碼方塊內的**外部**迴圈下方。代理不需要重複執行這個代碼方塊，這是一個新動作的開始。

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
**填充鵝卵石**與**挖掘地面**的步驟非常類似。我們可以複製前面寫好的挖掘地面的代碼方塊，將其放在 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 之後，僅將 ``||agent:Agent 破壞 [下]||``代碼方塊替換為 ``||Agent:Agent 放置 [下]||``代碼方塊。

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
再次測試你的代碼。注意，這次代理會挖掘地面，然後用 **鵝卵石** 替換它。這形成了噴泉底座的框架。

接著我們在噴泉底座框架內部挖掘。我們需要編寫代碼讓代理挖掘噴泉底座內部的地面，以防止噴泉水淹過底座。

## 步驟 10
拖放一個 ``||agent:Agent 移動 [左]||`` 代碼方塊，將方向改為 **左**邊，並將其放在當前代碼的最後。

再獲取另一個 ``||agent:Agent 移動 [前]||`` 代碼方塊，保持方向為 **前**方，並將其放在當前代碼的最後。

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
    agent.move(LEFT, 1)
    agent.move(FORWARD, 1)
})
```

## 步驟 11
將一個 ``||Loops:重複 [3] 次||`` 代碼方塊拖放到你的 ``||player:玩家 在聊天指令為||`` 代碼方塊的末尾，並將次數設為 **3**。

在噴泉底座框架的中心有一個 3 x 3 的草地，代理需要挖掘。因此，我們需要給它三個挖掘的動作，並重複這三個挖掘的動作三次。同樣，我們將第一個迴圈稱為**外部**迴圈，第二個迴圈稱為**內部**迴圈。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {

  }
})
```

## 步驟 12
再放入一個 ``||Loops:重複 [3] 次||`` 代碼方塊。將其放在第一個迴圈內，並將次數設為 **3**。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {

      }
  }
})
```

## 步驟 13
接下來，讓你的代理破壞 ``||agent:Agent 破壞 [下]||``，將方向設置為 **下**。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
      }
  }
})
```

## 步驟 14
讓你的代理往前移動 ``||agent:Agent 移動 [前]||``，並將其距離設為 **1**。

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
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
  }
})
```

## 步驟 15
接著讓你的代理退回到原來位置。放置 ``||agent:Agent 移動 [後]||``，並將距離置為 **3**。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
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
讓你的代理向左移動一步 ``||agent:Agent 移動 [左]||``。

這將使你的代理位於要移除的下一組三個方塊的開始位置。**外部**迴圈將確保這整個動作會重複三次。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
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
測試你的代碼，觀察你的代理挖掘噴泉底座框架的內部草地。

## 步驟 18
編寫噴泉水的特效。我們必須先讓代理去到噴泉底座的中間位置。
將一個 ``||agent:Agent 移動 [前]||`` 代碼方塊拖放到你的主代碼中。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
})
```

## 步驟 19
獲取一個 ``||agent:Agent 移動 [前]||`` 代碼方塊，將方向由**前**方改為**右**邊，並將距離改為 **2**。這將使你的代理位於噴泉底座的中心。
 
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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
})
```

## 步驟 20
獲取一個 ``||Loops:重複 [5] 次||`` 代碼方塊，將次數更改為 **5**。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {

  }
})
```

## 步驟 21
取得一個 ``||Agent:Agent 放置 [下]||`` 代碼方塊，並將其添加到你的代碼中，在 ``||Loops:重複 [5] 次||`` 迴圈內部。
這意味著你的代理將在噴泉底部放置五塊 **鵝卵石**。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
  }
})
```

## 步驟 22
取得一個 ``||agent:Agent 移動 [前]||`` 代碼方塊，將其添加到你的代碼中，並將方向改為**上**方。

這將使你的代理移動到噴泉的頂部，我們準備倒進噴泉水。

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
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
})
```

## 步驟 23
取得一個 ``||Agent:Agent 將物品槽 [1] 設爲使用中||`` 代碼方塊，添加到你的代碼中，並將其設置為 **2**，這是你的代理庫存中具有 **水桶** 的槽位，然後添加一個 ``||Agent:Agent 放置 [下]||``代碼方塊, 設定方向為**下**方。

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
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
  agent.setSlot(2)
  agent.place(DOWN)
})
```

## 步驟 24
檢查並測試你的代碼。然後將噴泉放置在公園的某個地方。