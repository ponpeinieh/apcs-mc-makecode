# 單元5：課程1 - 編寫風力發電場

## 步驟1
風力渦輪機組成了風力發電場。***風力渦輪機***類似於風車，當風吹到它們的葉片時會轉動。在現實生活中，當葉片轉動時，能量會轉換成電能。在我們開始建造風力發電場之前，讓我們考慮一個適合的位置。在我們的範例中，我們將使用城市附近的山丘。讓我們使用我們學到的方法編寫一個風力渦輪機，然後複製它來建造一個發電場。

```template
player.onChat("run", function(){
})
player.teleport(world(19, 79, -413))
```

## 步驟2
測試一下自己。現在我們已經到達最後一個單元，你應該對兩種主要的編碼建造方法 - ``||Agent:代理||``和``||Builder:建造者||`` -非常熟悉了。決定你想要使用哪種方法來建造你的風力渦輪機。在山丘上有一個範例提供你參考。

## 步驟3
如果需要的話，可以使用``||Blocks:方塊||``工具箱抽屜中的``||Blocks:複製||``代碼方塊來製作更多這樣的渦輪機。

```ghost
player.onChat("run", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
    blocks.fill(GRASS, world(0, 0, 0), world(0, 0, 0),FillOperation.Replace)
    agent.destroy(FORWARD)
    agent.place(FORWARD)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.teleportToPlayer()
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
        blocks.place(GRASS, world(0, 0, 0))
    }
    while (true) {
    	
    }
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
    builder.place(GRASS)
    builder.mark()
    builder.fill(GRASS)
})
```