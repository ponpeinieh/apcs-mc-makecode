### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 改變世界！

## 步驟 1
使用 ``||player: 玩家 在行動方式為 走路(walk) 時||`` 事件在特定的 ``||positions:世界 [0] [0] [0]||`` 座標位置設置一個方塊，這些座標是 **100, 68, 100**。創建一個 ``||variable:變數||`` 並將其命名為 **count**。拖動 ``||variable:變數 count 改變 1||`` 方塊和 ``||blocks:方塊 放置||`` 方塊，並添加 ``||variable:變數 count||`` 變數，這樣每次都會增加 1 並放置與該方塊 ID 關聯的方塊。1=石頭，2=草地，3=泥土，等等。使用另一個事件方塊，例如 ``||player: 玩家 在行動方式為 墜落(fall) 時||`` 來重置方塊。為此，拖動 ``||variable:變數 count 設爲||`` 設置為 **0** 以重新開始計數，並添加 ``||blocks:方塊 放置||`` 方塊，並添加 ``||variable:變數 count||`` 變數設置在相同的世界座標位置。這樣，每當你在世界中跳躍時，方塊將會重置。

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

