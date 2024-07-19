### @explicitHints 1

# 單元5 ：課程2 - 動畫風力發電場

## 步驟1
編寫三個渦輪機葉片模型。

在離你的風力發電場遠的地方找個空間，建立秘密模型，這些將用於動畫。這些地點可以是世界中的任何地方，只要確保從山丘上看不見它們。

在特定的旋轉位置創建你的第一個渦輪機葉片模型。在我們的示例中，我們使用了**黃色羊毛**來製作這些，但你可以用任何你喜歡的材料。必須根據最終動畫中希望看到的方向建造它們，所以建造它們時要面向你希望最終看到它們的方向。

記住，當你使用``||Blocks:複製||``工具時，複製的東西的方向始終是相同的。例如，如果一個建築物面向東方，它始終會面向東方。

## 步驟2
現在在這個模型旁邊創建另一個，但設計葉片處於另一個旋轉狀態。再創建第三個和最後一個不同旋轉狀態的葉片變化。

這三個建築是動畫的三幀。就像卡通或電影的幀一樣，快速連續播放它們，將產生運動的錯覺。

複製你第一台渦輪機上的模型葉片。接下來的階段是編寫模型葉片的移動代碼。我們將先處理一個模型葉片，然後後續再重複這些步驟來處理其他兩個風葉。

## 步驟3
選擇一個新的``||Player:on chat command||``代碼方塊，然後將文字更改為**wind_turbine**。

將一個``||Loops:重複 [4] 次||``代碼方塊拖到你的``||Player:on chat command||``塊中。出於測試目的，我們將保留它設置為**4**。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
    	
    }
})
```

## 步驟4
現在訪問``||Blocks:方塊||``抽屜並將``||Blocks:方塊 複製||``塊拖到你的``||Player:on chat command||``塊中。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        pos(0, 0, 0),
        pos(0, 0, 0),
        pos(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟5
用``||Positions:POSITIONS||``抽屜中的``||Positions:世界 [0] [0] [0]||``座標代碼方塊替換所有三個``||Positions:相對 ~[0] ~[0] ~[0]||``座標代碼方塊。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟6
右擊``||Blocks:方塊 複製||``代碼方塊，選擇**複製**以創建一個相同内容的代碼方塊，然後將其拖入你的代碼方塊中，放在第一個下面。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟7
重複以上動作，再創建一個複本，放置在下面，這樣你總共有三個``||Blocks:方塊 複製||``代碼方塊。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## 步驟8
返回你的渦輪機葉片模型，並注意你需要用它們在工作表中克隆的座標。將座標設置為每個建築的右上角和左下角，以創建包含整個葉片的不可見立方體。

**葉片組1** – 從：**55 78 -291** 到：**61 85 -291**

**葉片組2** – 從：**63 78 -291** 到：**69 85 -291**

**葉片組3** – 從：**71 78 -291** 到：**77 85 -291**

## 步驟9
輸入克隆座標。返回MakeCode，仔細輸入第一、第二和第三組葉片的座標到``||Blocks:從克隆||``代碼方塊中的``||Blocks:from||``和``||Blocks:to||``部分。暫時將``||Blocks:into||``設置為空白。

## 步驟10
返回到本單元的**課程1**中創建的風力發電結構。

## 步驟11
從你的渦輪機柱頂部開始，建造一個20個任何種類材料的方塊的塔。這是一個測試柱，讓你能找到最終座標。在我們的示例中，我們用了**黃色羊毛**來建造這個塔。

在你的工作表中記錄

這個塔最上方塊的座標。

## 步驟12
然後將這些添加到所有三個``||Blocks:從克隆||``代碼方塊的``||Blocks:into||``座標中。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
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

## 步驟13
測試克隆座標。在正式放置你的動畫之前進行一小部分測試。這部分是關於找出當你運行命令時葉片克隆在哪裡。這可能因為每個人放置它們的方向、它們的大小等而有所不同。

使用你的葉片的中心，從頂部到中心再從中心向下。在我們的示例中，我們用**橙色羊毛**標記了這一點。在你的工作表中寫下這些信息。

底部的水平部分告訴我們，我們的葉片動畫的中心比實際位置向右偏了三個方塊，所以我們可以稍後進行補償。

現在做同樣的高度測量，從塔的頂部到葉片動畫的中心，並在你的工作表中記錄。再次，我們用**橙色羊毛**標記了這一點，這次在左側。

頂部的垂直部分告訴我們，中心向上偏了四個方塊。現在使用另一種材料，從你的渦輪機的實際中心點測量，並根據方向和數字進行補償。

## 步驟14
我們找到了我們的動畫的新準確中心座標。站在這個最後的方塊上，獲取座標。在你的工作表中記錄這些，並將它們添加到你的代碼中的``||Blocks:into||``設置的座標中。

## 步驟15
現在運行你的代碼，看看你在渦輪機柱頂上是否有一個準確和正常工作的風葉。如果你的風葉不正確或不工作，根據需要進行其他調整。根據需要在你的工作表上使用空間進行筆記。

## 步驟16
當克隆正確時，移除你添加的測試方塊，以確定測試克隆偏離了多少。在這個例子中，將會移除**黃色、橙色**和**紅色羊毛**方塊。

不要刪除你的模型葉片！它們必須留在那裡，這樣你才能將它們克隆到其他渦輪機上。

動畫其他渦輪機在你的農場中。現在你完成了第一個，準備好動畫其他渦輪機。記住，你可以使用相同的模型座標，只需更改每個新渦輪機的``||Blocks:into||``座標輸入。
