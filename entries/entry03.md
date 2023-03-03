# Entry 3
##### 2/13/2023

### Context
After a few weeks of tinkering with kaboom, I have learned more information about how I can build my game. In my last blog, I wrote about how I went through the website and learned from examples shown in the Kaboom website. A goal that I talked about was exploring/learning more about the “scenes”.

### Part 1: Layers and sprites
For this part of the video, I learned how to make the floor of the game by using symbols.
First I will have to load in sprites.
 If I want to load in sprites from an website, I would need to use `loadRoot()` (__) = The website that stores all the sprites needed
→    `loadRoot ('https://i.imgur.com/') // the pathway to access all the images needed for the sprite`
→   ` loadSprite('coin', 'wbKxhcd.png') // the name you give the sprite, link to the sprite`

After that, I constructed a map of the game using symbols:
```java
 const map = [
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '                                       ',
                '==============================  =======', // the floor of the game
            ]
```


I assign the sprite to a symbol:
```java
const levelCfg = {
                width: 20,
                height: 20,
                '=': [sprite('block'),solid()]
            }
```
→ the width and the height sets the size of the sprites
→  the structure to assign the sprite to a symbol: `[sprite(‘_sprite name__’),solid()]`

Then I would have
`const gameLevel = addLevel(map,levelCfg)`
→ this would mean passing through the first level (which is the variable map that consists of the map) and the variable levelCfg which consists of the process of assigning the sprite to the symbol.

`addLevel` means construct the level based on the symbols

![img of floor](../tinker-img/floor.png)
→ the result

![img of overlap](../tinker-img/overlap.png)

![img of fixoverlap](../tinker-img/fixoverlap.png)

![img of mariobody()](../tinker-img/mario.jpg)
### EDP
I found this [video](https://www.youtube.com/watch?v=2nucjefSr6I) that teaches you how to create a game with Kaboom. This caught my eye because I am hoping that I will be able to learn more about scenes from this video.


### EDP + Skills
The engineering design process I am at right now is “research the problem” because I am looking at tutorials and videos to help me better learn the tool. The skills I learned while learning my tool are “how to learn” and “attention to detail” because in order to learn more about scenes and how to apply it to my project, I would need to know what components are being applied to make the scene work. During the times where I am tinkering on Kaboom, I also encountered problems that made my code not function properly. The problems I made were minor such as confusing “{“ with “(“ or spelling errors. This results in me paying more attention to my code so I make the same mistakes twice and avoid code results not displaying.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
