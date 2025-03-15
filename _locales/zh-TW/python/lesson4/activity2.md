### @explicitHints true

# 活動 2 - 飲食需求。

```python
blocks.place()
```

## 第一步
通過更改前 **4** 個 `||blocks: 放置方塊於位置||` 指令的值，將預定義列表中的所有食物給予 **第一隻** 狗。讓它們依次放置列表中的每一項。然後將箱子中的食物給予第一隻狗。

### ~ tutorialhint 
要從快捷欄中丟出物品，請按鍵盤上的 [**Q**] 鍵。

## 第二步
將列表中的所有食物以及額外的維生素給予 **第二隻** 狗。使用 **append** 方法將變數 **Vitamins** 添加到列表的末尾。
然後更改最後一個 `||blocks: 放置方塊於位置||` 指令的值，以便將維生素放入機器，然後將食物給予第二隻狗。

## 第三步
將列表中的所有食物（不包括 **牛肉**）給予 **第三隻** 狗。使用 **pop** 方法從列表中移除變數 **Beef**。
然後將食物給予第三隻狗。

### ~ tutorialhint 
使用 **pop** 方法時，必須使用列表的位置值，而不是名稱。

```template
Bone = world(-21, 45, -31)
Beef = world(-21, 45, -29)
Chicken = world(-21, 45, -27)
Biscuit = world(-21, 45, -25)
Vitamins = world(-21, 45, -23)
// 將以下行替換為你的程式碼 #   
Dog_Food=[Bone, Beef, Chicken, Biscuit]
//使用 append 方法將變數 Vitamins 添加到列表中 | 第二步
//使用 pop 方法移除變數 Beef                          | 第三步

blocks.place(REDSTONE_BLOCK, Dog_Food[0]) 
//更改以下列表的數值         | 第一步
blocks.place(REDSTONE_BLOCK, Dog_Food[0])
//更改以下列表的數值         | 第一步
blocks.place(REDSTONE_BLOCK, Dog_Food[0]) 
//更改以下列表的數值         | 第一步
blocks.place(REDSTONE_BLOCK, Dog_Food[0])   
//更改以下列表的數值                  | 第二步
blocks.place(REDSTONE_BLOCK, Dog_Food[0]) 
```
