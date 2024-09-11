### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1


# Make it rain!

## Step 1

Make it rain while you dance in Minecraft! To achieve this, follow these steps using specific blocks:

1. Create your variables, such as **walk**, **jump**.
2. Choose the event blocks, for example, ``||player: on player walk||`` and ``||player: on player fall||``.
3. For each corresponding event block, set your new ``||variable: variable||`` to ``||logic: true||``.
4. Use a ``||loops: forever||`` block and insert a ``||logic: if statement||`` inside it. Set the condition to check if all your variables are ``||logic: true||`` (using **and** to combine the conditions). Then, within the ``||logic: if statement||``, add the ``||gameplay: set weather to||`` block and set it to **rain**.

### ~ tutorialHint
```blocks
let walk = false
player.onTravelled(WALK, function () {
    walk = true
})
loops.forever(function () {
    if (walk == true && "" == "") {
    	
    }
})

```

```ghost
let climb = false
let walk = false
let _break = false
player.onTravelled(CLIMB, function () {
    climb = true
})
player.onTravelled(WALK, function () {
    walk = true
})
blocks.onBlockBroken(STONE, function () {
    _break = true
})
loops.forever(function () {
    if (walk == true && climb == (true && _break == true)) {
        gameplay.setWeather(RAIN)
    }
})
```
