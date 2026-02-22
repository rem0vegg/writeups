# Wifies_Lover #1

> The old capital is silent. Concrete skeletons stretch into the sky where surveillance towers once stood. The Government called it stability. The people called it control. Somewhere in the wreckage, the Resistance has rebuilt. Not openly. Not recklessly. You have received an image. The image is not decoration. It is not scenery. It is not random. It shows the location of a functioning Resistance relay — one of the few places where real technology still operates.

>Usage of the /guess Command /guess (Coordinate_X) (Coordinate_Y) (Coordinate_Z) For example if the coordinates were 100,100,100 the usage for /guess would be /guess 100 100 100 VERSION:1.21.8

>minecraft.bitskrieg.in:25565

For this challenge, we were handed an image showing a location maintained by the Resistance, basically one of the last spots where technology still actually works. The twist? The image wasn’t just for decoration. It contained the exact clues we needed to find the place in Minecraft. The goal was simple: figure out the location, get the coordinates, and submit them using `/guess`.

![Attachment Image](https://i.imgur.com/0btMSmw.png)

The attached file, `2026-02-19_00.20.22.png`, was our starting point. I first studied the image to pick out key details for the search. What stood out were broken concrete walls, the heights and counts of windows, and the presence of trees near the structures. These little things would make or break the search in-game.

![My analysis of the image](https://i.imgur.com/S6b8Q4O.jpeg)

Logging into the server (`minecraft.bitskrieg.in:25565`) with a tiny view distance of just 4 chunks made things tricky. Looking south first, I spotted a building with broken walls and short windows (height 2). Then, glancing north, I saw another building with broken walls but taller windows (height 4). Naturally, I went there first, but it didn’t match the image. No tree at the wall’s edge.

![Looking North](https://i.imgur.com/0o3SSW8.png)
![No Tree](https://i.imgur.com/2uJNErn.png)
![Other building](https://i.imgur.com/89ne315.png)
![Exact building](https://i.imgur.com/qSFOOjE.png)

Using that tree as a clue, I scouted the area a bit more and eventually found the right structure. Broken walls, tall windows, and the tree exactly where it should be. Matching the perspective from the image to what I saw in-game, I locked in the coordinates.

```
x: 522
y: 60
z: 754
```

A quick `/guess 522 60 754` later, and boom, the server gave me the flag:

```
BITSCTF{G0D5p33d_F3ll0w_reb3l}
```

![Coordinate](https://i.imgur.com/y3Vewzr.png)

---

### Takeaway

This challenge was a lot of fun because it focused on **visual observation and exploration**. Small environmental details like window heights and trees were critical. It felt like a scavenger hunt in Minecraft and nothing beats finding the exact spot and seeing the flag appear. Out of all the challenges I have done, I enjoyed this one the most because AI cannot solve it, you actually have to run Minecraft 😂

---

### tl;dr

* Analyze the attached image and note distinguishing features: broken walls, window height, trees
* Enter the server `minecraft.bitskrieg.in:25565` with low view distance
* Scout the area using key features from the image
* Identify the correct structure based on tree placement and window height
* Match in-game perspective to the screenshot
* Submit coordinates with `/guess 522 60 754`
* Receive the flag: `BITSCTF{G0D5p33d_F3ll0w_reb3l}`


