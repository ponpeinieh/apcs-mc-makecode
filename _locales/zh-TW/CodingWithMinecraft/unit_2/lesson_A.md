### @explicitHints 1

# 活動：黃磚路

## 第一步  
監聽走路事件。將 ``||Player: 玩家 在行動方式為 走路(walk) 時||`` 方塊拖曳到編碼工作區。

### ~ tutorialhint
``` blocks
         player.onTravelled(WALK, function () {
	
})
```

## 第二步  
放置一些草地。將 ``||Blocks: 方塊 放置於||`` 方塊拖曳到 ``||Player: 玩家 在行動方式為 走路(walk) 時||`` 方塊下方，直到聽到並看到它卡入位置。

### ~ tutorialhint      
``` blocks
         player.onTravelled(WALK, function () {
   		 blocks.place(GRASS, pos(0, 0, 0))
})
```

## 第三步  
放置一朵花。使用下拉選單將 ``||Blocks: 方塊 放置於||`` 中的 **草地** 方塊替換為 **蒲公英**（黃色花朵）。

### ~ tutorialhint
``` blocks
         player.onTravelled(WALK, function () {
    blocks.place(YELLOW_FLOWER, pos(0, 0, 0))
})
```

## 第四步  
進入 Minecraft 並開始行走一兩秒。轉身看看你留下的花徑。如果你向後走，你可以看到花朵從地面冒出。

## 第五步：試試黃金！

添加黃金。將 ``||Player: 玩家 在行動方式為 走路(walk) 時||`` 方塊拖曳到編碼工作區。添加 ``||Blocks: 方塊 放置於||`` 方塊並放置黃金而不是花朵。

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.place(GOLD_BLOCK, pos(0, 0, 0))
})
```

## 第六步  
觀察發生了什麼。這是一個不錯的想法，但還不是你想要的效果。你實際上在身後留下了一堵黃金牆，這有點不方便。你該如何將這些方塊沉入地面，讓它們形成一條黃磚路呢？

## 第七步  
修改 Y 坐標。讓我們將 **Y** 坐標 **減去 1**，這樣磚塊的底部就會下降一層。

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.place(GOLD_BLOCK, pos(0, -1, 0))
})
```

## 第八步  
製作一條真正的磚路。從遊戲中看看效果，然後從 ``||Blocks: 方塊||`` 選單中 **添加** 一個不同的方塊！

### ~ tutorialhint
``` blocks
player.onTravelled(TravelMethod.Walk, function () {
blocks.fill(
GOLD_BLOCK,
pos(-1, -1, -1),
pos(1, -1, 1),
FillOperation.Replace
)
})
```