### @explicitHints 1

# 單元 5：課程 3 - 編碼照明系統  

## 步驟 1

我們把課程2的動畫，再延申一步，加入風力發電後產生的照明結果。也就是當渦輪葉片轉動一段時間後，產生了電力，這個電力讓燈具點亮。

首先我們必須手動挖掘一個溝渠，然後佈置紅石綫路，連接紅石燈。

在風力渦輪底座的正後方，您需要挖一條**兩個方塊深、五個方塊長**的溝槽，在溝槽最後一個方塊位置填入一個草地方塊，形成一個階梯上到地面。

將**紅石粉**佈置在方塊 2、3、4、5 和 6 上(5和6實際上是同一個方塊的連結的兩個面上)。而方塊 1(最靠近風力渦輪底座的方塊) 則不放紅石粉。這裏是預留放置**紅石方塊**的地方，做爲紅石訊號的來源。在溝槽末端的地面上放置**紅石燈**。 

<img src="https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/redstone.png" alt="紅石綫路圖片" width="200"/>

## 步驟 2
在課程2最後步驟的迴圈之前加入一個``||Blocks:方塊 放置 [方塊] 在||``代碼方塊。  

```template
player.onChat("wind_turbine"，function () {
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    blocks.place(GRASS，pos(0，0，0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 3
使用下拉選單將 ``||Blocks:方塊 草地||`` 更改為 ``||Blocks:方塊 紅石方塊||``。

接著打開``||positions:座標||``抽屜，將``||positions:世界 [0] [0] [0]||``代碼方塊拖到你的編程工作區。
然後替換掉``||blocks:方塊 填充||``代碼方塊中的``||positions: 相對||``位置代碼方塊。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    blocks.place(REDSTONE_BLOCK，world(0，0，0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟 4 
回到步驟1中標記為**方塊 1**(最靠近風力渦輪底座的方塊)**上方**的位置，取得它的坐標，填入到``||blocks:方塊 填充||``代碼方塊中的``||positions:世界 [0] [0] [0]||``代碼方塊。這個位置的座標，在我們的例子中坐標為 **(7，81，-412)**。

在這個位置放置**紅石方塊**，將替我們的紅石訊號綫路提供**電力來源**，並且連通紅石訊號綫路，讓末端的**紅石燈**亮起.

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```
## 步驟 5
在迴圈之後再加入一個``||Blocks:方塊 放置 [方塊] 在||``代碼方塊。 注意是放在迴圈的外面。

您可以利用複製的方式，從剛剛**放置紅石方塊**的代碼方塊複製過來。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
})
``` 

## 步驟 6
使用下拉選單將 ``||Blocks:方塊 紅石方塊||`` 更改為 ``||Blocks:方塊 空氣||``。

於是紅石訊號綫路將失去訊號來源，於是斷絕了綫路，熄滅了紅石燈。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR，world(7，81，-412))
})
```

## 步驟 7
測試你的代碼。如果成功，每次運行你的 **wind_turbine** 命令時，渦輪葉片將旋轉，然後點亮**紅石燈**，接著葉片停止，紅石燈也熄滅。  

## 步驟 8
取得 ``||Loops:重複無限次||`` 代碼方塊。這個代碼方塊創建一個永遠運行不停止的迴圈。
所以我們可以讓我們的動畫不停地重複執行。

## 步驟 9
將``||Loops:重複無限次||`` 拖到編碼工作區，然後將名稱為 **wind_turbine**的``||player:玩家 在聊天指令為||``代碼方塊中的所有代碼，拖到``||Loops:重複無限次||``中。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR，world(7，81，-412))
    )
})
```   

## 步驟 10
將這個 ``|||Loops:重複 [10] 次||`` 中的次數改為 **20**。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR，world(7，81，-412))
    )
})
```      

## 步驟 11
我們如何模擬風力的變化呢? 

我們如何模擬沒有風時，渦輪靜止的狀況? 到目前為止，我們的渦輪機做無休止地轉動，紅石燈快速地點亮然後熄滅。我們可以在這段代碼中加入恰當的**暫停**，這樣就會帶來這種**風停**的效果。

## 步驟 12
返回 ``||Loops:迴圈||`` 抽屜並選擇 ``||Loops:暫停 (毫秒)||`` 代碼方塊。將其拖放到你的代碼中，放在最後一個 
``||Blocks:方塊 放置 [] 在空氣||``代碼方塊之後。將時間數字設為 **5000**毫秒。

5000毫秒(ms)也就是5秒鐘，這將使我們的動畫暫停5秒。模擬風力發電暫停5秒的效果。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
   
})

loops.forever(function () {
    blocks.place(REDSTONE_BLOCK，world(7，81，-412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
        world(39，70，-433),
        world(45，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(31，70，-433),
        world(37，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(23，70，-433),
        world(29，76，-433),
        world(4，95，-408),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR，world(7，81，-412))
    loops.pause(5000)
    )
})
```

## 步驟 13
運行測試你的代碼。你的風葉片現在應該轉動20次，然後停止5秒，並且會無限次地重複下去。你的 **紅石燈** 應該只在渦輪葉片轉動時亮起。