### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 建造

## 步驟 1
給自己至少 **34 顆翡翠** 方塊。創建一個新的 ``||variable:變數||`` 並將其命名為 **count**。取得一個 ``||blocks:方塊 在被放置的方塊為 時||`` 方塊並將其設為 **翡翠**。將 ``||variable: 變數 count 改變 1||`` 方塊拖到 ``||blocks:方塊 在被放置的方塊為 時||`` 中，並添加 ``||player: 玩家 説出||`` 方塊。在 ``||player: 玩家 説出||`` 方塊中添加 ``||variable:count||``。這樣，每當你放置方塊時，遊戲將會計算你放置了多少個方塊。

### ~ tutorialhint

你可以選擇鐵、金、翡翠或鑽石。

```blocks
let count = 0
blocks.onBlockPlaced(EMERALD_BLOCK, function () {
    count += 1
    player.say(count)
})

```

```ghost
blocks.onBlockBroken(STONE, function () {
    count += 1
    player.say(count)
})
let count = 0
mobs.give(
mobs.target(NEAREST_PLAYER),
STONE,
1
)

```


