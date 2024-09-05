### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 種植甜菜！

## 步驟 1

提供了兩個函數 **plantSeed** 和 **plantSection**。創建一個新的 ``||player: 在聊天指令為||`` 指令並在其中添加 ``||functions: 呼叫 plantSection||``。添加一個 ``||logic: 如果||`` 語句來檢查 ``||agent: agent 偵查 方塊下||``。
如果方塊下是 ``||blocks: 青金石方塊||``，則代理需要 ``||agent: 轉動 右||``、``||agent: 移動 前||`` 和 ``||agent: 轉動 右||``。
``||logic: 否則||`` 如果代理 ``||agent: 偵查 方塊 下||`` 是 ``||blocks: 石英方塊||``，則代理需要 ``||agent: 轉動左||``、``||agent: 移動前||`` 和 ``||agent: 轉動左||``。
最後，``||functions: 呼叫 plantSection||``。

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
})
```

```template
/**
 * 我們在函數內部呼叫了一個函數
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * 代碼被修改以避免在代理下方沒有方塊的情況下放置種子。
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* 你需要檢查代理是否站在青金石方塊上，則轉向右側，如果是石英方塊則轉向左側。
*/
```

## 步驟 2
在 ``||player: 在聊天指令為||`` 指令中添加 ``||logic: 如果||`` 語句。在 ``||logic: 如果||`` 塊的 **true** 部分添加一個 ``||logic: " " = " "||`` 塊。如果當 ``||agent: agent 偵查 方塊下||`` 是 **等於 (=)** ``||blocks: 青金石方塊||``，則代理需要 ``||agent: 轉動右||``、``||agent: 移動前||`` 和 ``||agent: 轉動右||``。

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }

})
```

```template
/**
 * 我們在函數內部呼叫了一個函數
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * 代碼被修改以避免在代理下方沒有方塊的情況下放置種子。
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* 你需要檢查代理是否站在青金石方塊上，則轉向右側，如果是石英方塊則轉向左側。
*/
```

## 步驟 3
點擊 ``||logic: 如果||`` 塊的 **+** 符號兩次。點擊 ** - ** 刪除 **else** 塊。將 ``||logic: " " = " "||`` 塊添加到 ``||logic: 否則如果||`` 塊的 **空白** 區域。如果 ``||agent: agent 偵查 方塊下||`` 是 **等於 (=)** ``||blocks: 石英方塊||``。則代理需要 ``||agent: 轉動左||``、``||agent: 移動前||`` 和 ``||agent: 轉動左||``。

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }

})
```

```template
/**
 * 我們在函數內部呼叫了一個函數
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * 代碼被修改以避免在代理下方沒有方塊的情況下放置種子。
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* 你需要檢查代理是否站在青金石方塊上，則轉向右側，如果是石英方塊則轉向左側。
*/
```

## 步驟 4
最後，在 ``||player: 在聊天指令為||`` 指令中添加另一個 ``||functions: 呼叫 plantSection||``，位於 ``||logic: 如果||`` 語句之外。

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
    plantSection()
})
```

```template
/**
 * 我們在函數內部呼叫了一個函數
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * 代碼被修改以避免在代理下方沒有方塊的情況下放置種子。
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* 你需要檢查代理站在什麼方塊上。如果站在青金石方塊上則轉向右側，如果是石英方塊則轉向左側。
*/

/**
* 你可以點擊 “+” 按鈕來添加一個 else
*/

```

```ghost
player.onChat("turn", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
    plantSection()
})
```