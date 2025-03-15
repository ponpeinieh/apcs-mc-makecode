### @explicitHints true
### @hideIteration true 
# 活動 1 - 動物分類。

```python
blocks.place()
mobs.spawn()
world(0, 0, 0)
```

## 第一步
編寫一個名為 **My_list** 的列表，列出 Minecraft 世界中從 **左** 到 **右** 的動物。
在已經提供的指令之後，再放置 **4** 個 `||mobs: 生成生物於位置||` 指令。使用圍欄上的標誌信息來完成這些指令。

### ~ tutorialhint 
記住，列表的位置從零開始。

```template 
location1 = world(-2, 40, -11)
location2 = world(-2, 40, -5)
location3 = world(-8, 40, -0)
location4 = world(-13, 40, -5)
location5 = world(-13, 40, -11)
//將以下行替換為你的程式碼 #   

//動物列表 

mobs.spawn(My_list[0], location1)
//在 location2 生成列表中的第三個生物
//在 location3 生成列表中的第五個生物
//在 location4 生成列表中的第二個生物
//在 location5 生成列表中的第四個生物
```
