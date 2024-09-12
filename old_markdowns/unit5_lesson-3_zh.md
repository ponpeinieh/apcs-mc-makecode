### @explicitHints 1

# 單元 5：課程 3 - 編碼照明系統  

## 步驟 1
編碼風力指示器。我們首先需要做的是創建一個假象，即風力渦輪的葉片不總是在轉動。就像現實生活中有時風力不足以使其轉動一樣。更改``||loops:repeat||``元素的值，從 **4** 改為 **10**。 

```template
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 2
生成電力。將一個``||Blocks:place [方塊] 在||``代碼塊拖放到您的代碼塊的第一部分，放在``||Loops:repeat [10] 次||``塊的上方。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 3
使用下拉菜單將 **Grass Block** 元素更改為 **Block of Redstone**。請記住，**Block of Redstone** 是我們在庫存中探索過的輸入方塊。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 4
將所有三個 **relative** 座標橢圓替換為 ``||Positions:POSITIONS||`` 工具抽屜中的 ``||Positions:world [0] [0] [0]||`` 座標橢圓。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 5
返回遊戲並站在您挖掘用於您的 **Redstone** 的壕溝中的第一個方塊上。在您的工作簿中記下此方塊的座標。在我們的例子中，這是 **8 81 -412**，但您的座標將是獨特於您自己的建築。

## 步驟 6
在 MakeCode 中，將這些新座標插入到您的 ``||Blocks:place [Block of Redstone]||`` 設置中。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 7
右鍵點擊您完成的 ``||Blocks:place [Block of Redstone]||`` 代碼塊並選擇 **Duplicate**。

將這個複製的、淡化的代碼塊拖放到主代碼塊的底部，放在第三個 ``||Blocks:clone from||`` 代碼塊之後，重要的是，在 ``||Loops:LOOP||`` 之外。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
})
``` 

## 步驟 8
使用下拉菜單將 **Block of Redstone** 元素更改為 **air**。到目前為止的完整代碼。你的完整代碼應該看起來像這樣，但要使用你自己的座標。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
})
```

## 步驟 9
測試你的代碼。如果成功，每次運行你的 **wind_turbine** 命令時，你的 **Redstone Lamp** 將會亮起。  

## 步驟 10
獲取 ``||Loops:forever||`` 代碼塊。  

這個代碼塊創建一個迴圈，並且永遠運行。這對於全局常量非常有用，比如天氣條件或者在這種情況下，風。

## 步驟 11
將其拖到編碼工作區，然後單擊並保持按住左鼠標按鈕在你的 ``||Blocks:place [Block of Redstone]||`` 代碼塊上。在拖動鼠標時保持左鍵按下，將此代碼塊及其下方所有附加的代碼塊拖放到新的 ``||Loops:forever||`` 塊中。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```   

## 步驟 12
將這個 ``||Loops:repeat [10] 次||`` 中的數字更改為 **20**。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```   

## 步驟 13
模擬風力變化。最後，我們需要添加一些內容，表示沒有風活動的時期。到目前為止，我們的渦輪機無休止地轉動，電源快速開啟和關閉。在這段代碼中恰當的暫停將給我們帶來這種效果。

## 步驟 14
返回 ``||Loops:LOOPS||`` 菜單並選擇 ``||Loops:pause (ms)||`` 代碼塊。將其拖放到你的代碼中，並將其放在最後一個 ``||Blocks:place [Air]||`` 代碼塊之後。然後將數字設置為 **5000**。

作為指南，1000ms 是遊戲內時間的一秒。因此，將其設置為5000ms將使我們的動畫暫停5秒。模擬風力停電5秒的效果。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
   
})
loops.forever(function () {
    for (let index = 0; index < 20; index++) {
        blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    loops.pause(5000)
})
```

## 步驟 15
運行你的代碼。測試你的代碼。你的風葉片現在應該轉動20次，然後停止5秒，並在無休止迴圈中進行。你的 **Redstone Lamp** 應該只在風葉片轉動時亮起。如果它沒有工作，回到代碼中進行審查並進行必要的調整。然後，你可以重複這些步驟來完成你的其他渦輪機。