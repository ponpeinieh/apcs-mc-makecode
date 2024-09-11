### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 改變世界！

## 步驟 1
使用 ``||player: 玩家 在行動方式為 走路(walk) 時||`` 事件，在指定的 ``||positions: 世界 [0] [0] [0]||`` 坐標 (**100, 68, 100**) 放置方塊。創建一個名為 **count** 的 ``||variable: 變數||``，該變數將作為方塊 ID。然後，加入 ``||variable: 變數 count 改變 1||`` 方塊和 ``||blocks: 方塊 放置||`` 方塊，並使用 **count** 作為方塊 ID。每次 **count** 增加 1，將放置相應的方塊：例如，當 count = 1 時放置石頭，count = 2 時放置草方塊，count = 3 時放置泥土，依此類推。

要重置方塊 ID，請使用另一個事件，例如 ``||player: 玩家 在行動方式為 墜落(fall) 時||``。在此事件中，拖動 ``||variable: 變數 count 設爲||`` 方塊，並將 **count** 設為 0。然後，再次使用 ``||blocks: 方塊 放置||`` 方塊，並使用 ``||variable: 變數 count||`` 作為方塊 ID，在相同的坐標放置方塊。如此一來，每當你在世界中跳躍時，方塊將會重置為初始狀態。

### ~ tutorialhint 
不要忘記使用 ``||positions:世界 [0] [0] [0]||`` 來指示座標。


```blocks
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
```


```ghost
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
player.onTravelled(FALL, function () {
    count = 0
    blocks.place(count, world(100, 68, 100))
})
```

