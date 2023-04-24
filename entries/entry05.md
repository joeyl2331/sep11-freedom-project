# Entry 5
##### 4/22/23

### Content
By now me and my partner have finished learning about the key componenets from Kaboom that we needed to build our freedom project game. From the [Freedom Project MVP Plan](https://docs.google.com/document/d/1szrDrbG5V1n9tMBLlT8e83kK7NH4SLwHRD-YPeLCInE/edit) our goal was to make sure that we have a working game before April 17th. 

### Finalizing Game
#### Step 1
After loading in the sprites to the game that me and my partner have created (mentioned in the last blog), we moved on to the next step of our plan.
#### Step 2
If it is a game, then the sprites would have to move around. This is where we used the `keydown` component to give our sprite the ability to move left, right, up, and down freely.
```java
// directions
  const dirs = {
    "left": LEFT,
    "right": RIGHT,
    "up": UP,
    "down": DOWN,
  }

  
  for (const dir in dirs){
    onKeyDown(dir,() => {
      player.move(dirs[dir].scale(300)) // movement speed
    })
  }
```
#### Step 3
After we have gotten the sprites to move, we figured that we needed to somehow setup the game. If we want our sprite to go from one level to another, then we would have to create scenes.
```java
// level 1
    [
      "=========================|===",
      "=p x x  x     x       xx    =",
      "=  x           x      x     =",
      "=    x  x           xx   x  =",
      "= x  x     o      xx    x   =",
      "=   x   x     x x           =",
      "=          xxx              =",
      "=   x            x     x    =",
      "=        x     xx       x   =",
      "=     x    x x   x  x       =",
      "=x        x    x x x    kxx =",
      "=    x       xxx     x      =",
      "=============================",
      ], 
```
Our first level started off easy. The sprite (p) could easlily obtain the key (k) and exiting the door (|) withoout touching the enemy (x) on the page. 
#### Step 4
After seting up the first level, me and my partner have decided to create more levels to the game. As the levels get higher, then there would be more difficulty to the game.
```java
// level 3
    [
      "=========================|===",
      "=p  x   x xx     x    xxx   =",
      "=   x           o      x    =",
      "= xx o  x xx      x   x   o =",
      "= x              xx    x    =",
      "=   x   x x     x  ko   x   =",
      "=      x     xx  x    xx    =",
      "=   x     x  x x    x    x  =",
      "=    x    x     xx       x  =",
      "=   x xx  o   x x   x  x   x=",
      "=x           x x      x     =",
      "= x   x  x  x     x    x   x=",
      "=============================",
      ],
    // level 4
    [
      "=========================|===",
      "=p  x        x    o x o x   =",
      "=        o     o x      x   =",
      "= xxx o x  xx      x   x  o =",
      "= x  x            xx    x   =",
      "=   x     x    o x       x  =",
      "=      x      x  x   xxx    =",
      "=   o    xx  o xx    x    x =",
      "=       ko      xx     xx   =",
      "=   x xx      xx     xx     =",
      "=x           x x  o  xx  o  =",
      "= x xxx         x    xxx    =",
      "=============================",
      ],
    ]
```
As we see here in levels 3 and 4, there is a significant increase of enemies being added to the game. We have also put the key in different location in each level for the player to collect.
#### Step 5
After creating all the levels we needed for our game, we figured that there needed to be a lose and a win scene. 

However before that, I needed to write a code that allows the player to enter a lose or win scene depending on the results of their game. This is where I would use `player.onCollide()` learned from my last blog.
```java
player.onCollide("coin", (coin) => {
  destroy(coin)
})
```
This shows the coin disappering when the sprite touches the coin.
```java
player.onCollide("key", (key) => {
  destroy(key)
  hasKey = true // player has key
})
```
This shows the key disappering when the sprite touches the key.
```java
player.onCollide("door", () => {
    if (hasKey){ // has key
      // go next level
      if(levelIdx + 1 < levels.length){ 
          go("main", levelIdx + 1)
      } else { // player was on the last level
          go("win")
      }
    } else { // has no key
      dialog.text = "you need a key!" // the dialog that would appear on the screen if the character touches the door AND has no key
    }
})
```
This shows how when only when the sprite has the key and touches the door, then the door will open for the sprite to go on to the next level. Otherwise, the player will be stuck on the level that they are on, until they have collected the key.
```java
// lose scene
scene("lose", () => {
  add([
    text("You Lose"),
    pos(width()/2, height()/2),
    origin("center"),
  ])
})

// sprite touches owl and goes to lose scene
player.onCollide("character", () => {
  go("lose")
})
```
The player will be lead into the lose scene if their sprite touched the enemy. 
```java
scene("win", () =>{
  add([
    text("YAYYY You Win!"),
    pos(width()/2, height()/2),
    origin("center"),
  ])
})
```
The player will be lead into the win scene if they have passed all four levels of the game.

### Links
* [Code to the game](https://replit.com/@joeyl2331/kaboommvp#code/main.js)
* [Final result of the game](https://kaboommvp.joeyl2331.repl.co/)

### EDP + Skills
The engineering design process I am at right now is "create a prototpye". From what you can from this blog entry, me and my partner have successly made a game where the player can have interactions with the sprites on the page. Skills I learned when creating a prototype of my game was communication organization. By having better communication with my partner, we were able to finish making the MVP of the game on time. By having better organization of the code, there were less errors made. And by commenting our code, it made it easier for us to debug the code when needed.

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
