### @explicitHints 1

# 單元5 ：課程2 - 動畫風力發電場

## 步驟1
在離你的風力發電場遠一點的地方，找個平坦的空間，我們將建立渦輪機**葉片**模型，它們將用於動畫之中。

你可以使用任何你喜歡的材料做爲葉片的材料，範例裏使用了**青色羊毛**。但是所建立的葉片模型的**方向**很重要。因爲我們最終必須將這些葉片模型**複製**到風力渦輪機上。

你必須根據最終動畫中希望看到葉片的方向建造它們。也就是你必須先確認風力渦輪機的葉片面向的方位(它是不是面向**南方**?)。

記住，當你使用``||Blocks:複製||``工具時，複製的東西的方向始終是相同的。例如，如果一個建築物面向東方，它始終會面向東方。

## 步驟2
首先我們建立**三個**渦輪機葉片**未裁剪**前的原始模型。

我們可以先建立一個未裁剪葉片模型，完成後再利用複製功能產生另外兩個。

這個未剪裁的葉片是一個**7x7**方塊大小的正方形墻壁。我們可以使用``||blocks:方塊 填充||``代碼方塊來建造。整個墻面主體是**青色羊毛**，但在中央放置了一個**黃色羊毛**做爲標記。

![預計葉片地點圖片](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/blade_location.png)

![預計葉片地點圖片](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/blade_1.png)

#### ~ tutorialhint
``` blocks
player.onChat("wind_blade"，function () {
    blocks.fill(
    CYAN_WOOL,
    world(39，70，-433),
    world(45，76，-433),
    FillOperation.Replace
    )
    blocks.place(YELLOW_WOOL，world(42，73，-433))
})
```
 
## 步驟3
在這個未裁剪的葉片模型旁邊，用複製方式再創建另外兩個相同的模型。當我們將這三個模型裁剪成我們想要的葉片樣式之後，這三個模型就是動畫的三幀(frame)。就像卡通或電影的幀一樣，快速連續播放它們，將產生運動的錯覺。

我們可以利用``||Blocks:方塊 複製||`` 代碼方塊來創建另外兩個相同的模型。

#### ~ tutorialhint
``` blocks
player.onChat("clone_wind_blade"，function () {
    blocks.clone(
    world(39，70，-433),
    world(45，76，-433),
    world(31，70，-433),
    CloneMask.Replace,
    CloneMode.Normal
    )
    blocks.clone(
    world(39，70，-433),
    world(45，76，-433),
    world(23，70，-433),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟4
在裁剪我們想要的葉片樣式之前，我們先測試是否可以成功地複製到風力渦輪機上。

我們將先處理第一個模型葉片，然後後續再重複這些步驟來處理其他兩個葉片。

我們知道山上的風力渦輪機面向南邊。你必須先確認渦輪葉片的中心的坐標，是不是位於(7，98，-408)位置之上? 我們可以由此而計算出它的左下角位置，即(4，95，-408)。這也是我們要將山下的葉片模型複製的位置。

我們可以利用``||Blocks:方塊 複製||`` 代碼方塊來測試。

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_1"，function () {
    blocks.clone(
    world(39，70，-433),
    world(45，76，-433),
    world(4，95，-408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟5
爲了測試第二個及第三個葉片是否也可以複製成功，我們先把上一步複製的葉片清除掉。

#### ~ tutorialhint
``` blocks
player.onChat("remove_blade"，function () {
    blocks.fill(
    AIR,
    world(4，95，-408),
    world(10，101，-408),
    FillOperation.Replace
    )
})
```

## 步驟6
接著我們測試第二個葉片是否可以複製成功。

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_2"，function () {
    blocks.clone(
    world(31，70，-433),
    world(37，76，-433),
    world(4，95，-408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```


## 步驟7
同樣地，我們先把上一步複製的葉片清除掉。然後測試第三個葉片是否可以複製成功。

#### ~ tutorialhint
``` blocks
player.onChat("test_blade_3"，function () {
    blocks.clone(
    world(23，70，-433),
    world(29，76，-433),
    world(4，95，-408),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## 步驟8
現在我們可以將牆壁裁切成我們想要的葉片形狀。

![完成葉片圖片](https://raw.githubusercontent.com/ponpeinieh/apcs-mc-makecode/master/computing/unit-5/blades.png)


## 步驟9
最後我們完成這個動畫。

選擇一個新的``||Player:on chat command||``代碼方塊，然後將文字更改為**wind_turbine**。
將一個``||Loops:重複 [4] 次||``代碼方塊拖到你的``||Player:on chat command||``塊中。將次數設為**10**。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine"，function () {
    for (let index = 0; index < 10; index++) {
    	
    }
})
```

## 步驟10
我們將前面測試的三個葉片複製的代碼複製到迴圈之中。測試你的動畫效果。

#### ~ tutorialhint
``` blocks
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