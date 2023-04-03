# Entry 4
##### 3/13/23

### Content
During the past few weeks, I have been continuing to learn my tool. I started working towards the MVP (minimum viable product) for my freedom project by first creating the sprites needed for my game.

Me and my partner used [pixelart](https://www.pixilart.com/) to create the sprites.   
The sprites we created are:  
Owl, door, koala, key, coin, and block

![owl](https://user-images.githubusercontent.com/91750499/226219884-cb15141b-4f7f-41ad-8a74-7a11fb630285.png)
![door](https://user-images.githubusercontent.com/91750499/229255806-54cf049a-07ef-4ba3-885d-5fbe7ec88d62.png)
![koala](https://user-images.githubusercontent.com/91750499/226217471-cc73ab54-22c8-475f-9af4-61c250ae4ff9.png)
![key](https://user-images.githubusercontent.com/91750499/226219003-17be3e4a-09d4-45e3-9953-86491ddd1bd9.png)
![coin](https://user-images.githubusercontent.com/91750499/226217476-38f84490-37f2-41d3-8479-7c0b793ca6b1.png)
![block](https://user-images.githubusercontent.com/91750499/229367777-302639bb-34e6-4045-8bb8-59353841acd9.png)

After creating the sprites, I used what I learned from the video mentioned in my last blog entry and from the kaboom website to help me make a type of thing that will allow my player to go to the next level. 

I know that if my game needs two levels, then I would need to create two scenes. 
```java
const levels = [
                [
                                    // level 1
                ],
                [
                                    // level 2
                ]
            ]
```
-> Inside the brackets labled "level 1" and "level 2" is where I would format how the game looks by adding in the symbols (representing the sprites)

From the code on the [website](https://kaboomjs.com/doc/21-scenes), I see that by using `onCollide()`, the player can move to the next level when their sprite touches a specific object.  
```java
// when the sprite touches the portal in the game
	player.onCollide("portal", () => {
		play("portal") 
		if (levelIdx < LEVELS.length - 1) { // if there are more levels after the current level that the user is in
      // go to the next level
			go("game", { 
				levelIdx: levelIdx + 1,
				score: score,
			})
		} else {
			// Otherwise player have reached the end of game, will go to "win" scene
			go("win", { score: score, }) 
		}
	})
```

### EDP + Skills
The engineering design process I am at right now is ""

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
