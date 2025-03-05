### @explicitHints 1
# 活動：漢堡 

## 第一步
建立一個函數。在 ``||Functions:函數||`` 工具箱抽屜中，點擊 **建立函數** 按鈕。

為函數命名。將此函數命名為 *bottomBun()*，然後點擊 **確定**。

## 第二步
建立 meat()、lettuce()、tomato()、topBun() 函數。重複上一步驟，建立另外四個函數，分別命名為：**meat**、**lettuce**、**tomato** 和 **topBun**。

## 第三步
將一個 ``||Player:玩家 在聊天指令為||`` 方塊拖到工作區。

將此 ``||Player:玩家 在聊天指令為||`` 重新命名為 **"burger"**。

## 第四步
將五個方塊 ``||Functions:呼叫函數 bottomBun||``、``||Functions:呼叫函數 meat||``、``||Functions:呼叫函數 lettuce||``、``||Functions:呼叫函數 tomato||`` 和 ``||Functions:呼叫函數 topBun||`` 拖入 ``||Player:玩家 在聊天指令為 "burger"||`` 中。

**注意**：這些函數的呼叫順序非常重要。

### ~ tutorialhint
```blocks
function lettuce()  {

}
function bottomBun()  {

}
function topBun()  {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function meat()  {

}
function tomato()  {

}
```

## 第五步
建立底部麵包。首先，您需要建立底部麵包。

將一個 ``||Blocks:方塊 填充||`` 方塊拖入 ``||Functions:bottomBun||`` 函數中。點擊下拉選單，將方塊更改為 **橡木木板**。

## 第六步
輸入底部麵包的坐標，起始位置為 **(~3, ~0, ~3)**，結束位置為 **(~8, ~0, ~8)**。

### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {

}
function tomato() {

}
```

## 第七步
“烹飪”肉片。讓我們建立一層肉片。將一個 ``||Blocks:方塊 填充||`` 方塊拖入 ``||Functions:meat||`` 函數中。

從下拉選單中選擇 **棕色陶土** 來調整材料。然後將坐標的起始位置更改為 **(~4, ~1, ~4)**，結束位置更改為 **(~7, ~1, ~7)**。

複製它。

### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {

}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}
```

## 第八步
建立生菜。讓我們建立一層生菜。將一個 ``||Blocks:方塊 填充||`` 方塊拖入 ``||Functions:lettuce||`` 函數中。

從下拉選單中選擇 **石灰混凝土** 來更改材料。然後將坐標的起始位置更改為 **(~4, ~2, ~4)**，結束位置更改為 **(~7, ~2, ~7)**。

### ~ tutorialhint
```blocks
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
     blocks.fill(
    LIME_CONCRETE,
    pos(4, 2, 4),
    pos(7, 2, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {

}
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
function tomato() {

}
```

## 第九步
建立番茄。讓我們建立一層番茄。將一個 ``||Blocks:方塊 填充||`` 方塊拖入 ``||Functions:tomato||`` 函數中。

從下拉選單中選擇 **紅色混凝土** 來更改材料。然後將坐標的起始位置更改為 **(~4, ~3, ~4)**，結束位置更改為 **(~7, ~3, ~7)**。

### ~ tutorialhint
```blocks
function tomato() {
    blocks.fill(
    RED_CONCRETE,
    pos(4, 3, 4),
    pos(7, 3, 7),
    FillOperation.Replace
    )
}
tomato()
```

## 第十步
建立頂部麵包。最後一個函數是 **頂部麵包**。為了讓漢堡看起來更真實，這個函數將填充兩層而不是一層。將兩個 ``||Blocks:方塊 填充||`` 方塊拖入 ``||Functions:topBun||`` 函數中。

將每個填充的材料更改為 **橡木木板**。

## 第十一步
首先更改頂部填充的坐標。坐標的起始位置應為 **(~3, ~4, ~3)**，結束位置應為 **(~8, ~4, ~8)**。

## 第十二步
底部填充的起始位置應為 **(~4, ~5, ~4)**，結束位置應為 **(~7, ~5, ~7)**。

### ~ tutorialhint
```blocks
function topBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 4, 3),
    pos(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    PLANKS_OAK,
    pos(4, 5, 4),
    pos(7, 5, 7),
    FillOperation.Replace
    )
}
topBun()
```

## 第十三步
完成程式！

### ~ tutorialhint
```blocks
function meat() {
    blocks.fill(
    BROWN_TERRACOTTA,
    pos(4, 1, 4),
    pos(7, 1, 7),
    FillOperation.Replace
    )
}
player.onChat("burger", function () {
    bottomBun()
    meat()
    lettuce()
    tomato()
    topBun()
})
function topBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 4, 3),
    pos(8, 4, 8),
    FillOperation.Replace
    )
    blocks.fill(
    PLANKS_OAK,
    pos(4, 5, 4),
    pos(7, 5, 7),
    FillOperation.Replace
    )
}
function tomato() {
    blocks.fill(
    RED_CONCRETE,
    pos(4, 3, 4),
    pos(7, 3, 7),
    FillOperation.Replace
    )
}
function bottomBun() {
    blocks.fill(
    PLANKS_OAK,
    pos(3, 0, 3),
    pos(8, 0, 8),
    FillOperation.Replace
    )
}
function lettuce() {
    blocks.fill(
    LIME_CONCRETE,
    pos(4, 2, 4),
    pos(7, 2, 7),
    FillOperation.Replace
    )
}
```
