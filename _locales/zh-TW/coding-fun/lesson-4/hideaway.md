### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# 竹子藏身處

## 步驟 1
編程代理在沙地的每一邊種植**3**個竹子。添加一個``||agent:Agent 轉動||``指令，確保代理可以完成這個任務。

#### ~ tutorialhint
應該有兩個**重複**循環，一個嵌套在另一個內部。

```ghost
player.onChat("bamboo", function () {
    for (let index = 0; index < 3; index++) {
        agent.setItem(BAMBOO, 64, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```

