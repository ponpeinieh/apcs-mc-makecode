### @explicitHints true
### @hideIteration true 
# 活動 3 - 一步一步來。

```python
blocks.place(GRASS_BLOCK, pos(0, 0, 0))
blocks.block_with_data(GRASS_BLOCK, 0)
```

## 第一步
編寫一些程式碼來建造一個完整的樓梯，使用 **磚塊**。你需要更改三個 `||blocks: 放置方塊於位置||` 指令中 **第二個** 參數的 **第二個** 和 **第三個** 坐標。你還需要更新 `||blocks: 方塊 帶數據||` 指令中的數據值。記住，每個數據值對應樓梯的方向。

### ~ tutorialhint 
查看牆壁以了解東、西、北和南的方向。
數據值：
0 = 西 (W)  
1 = 東 (E)  
2 = 北 (N)  
3 = 南 (S)  
 