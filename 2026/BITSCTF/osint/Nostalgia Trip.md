# Nostalgia Trip

> *"Go back in time maybe a decade or so, and play Geoguessr from a world you may or may not know. Enjoy :)"*

This challenge took me the longest to solve, and I didn’t document much while doing it, but here’s a structured summary of my approach, findings, and tools used.

The web-based challenge hosted **10 questions**, each providing a screenshot from different locations in **Hermitcraft Season 6**. The objective was to determine the exact in-game coordinates corresponding to each image.

![10 Soal](https://i.imgur.com/mXdf2Lw.png)

Here’s an example of one of the screenshots:

![Example](https://i.imgur.com/ledQpT1.png)

---

### Step 1 – Initial Attempt: 3D Map View

At first, I considered obtaining the Hermitcraft map to run locally, but then I found a **3D View Hermitcraft Map** online. This allowed me to solve roughly **4–5 questions** by matching visible landmarks in the screenshots with locations in the 3D map.

![3D Map View](https://i.imgur.com/SIzK0Pr.jpeg)

---

### Step 2 – Handling Interior Screenshots

Some questions were taken **inside buildings**, making it impossible to locate them with the 3D Map View. To solve these, I looked for a full map of **Hermitcraft Season 6** online and found it on the Hermitcraft Fandom page: [Map Downloads](https://hermitcraft.fandom.com/wiki/Map_Downloads).

I downloaded the world, imported it into my Minecraft client, and explored it to locate the interiors matching the screenshots.

---

### Step 3 – Using OSINT for Builder Identification

For certain interiors, I needed to identify **who built a specific structure** to find the location. I used open-source intelligence by checking Hermitcraft videos on YouTube. For example, one video that helped was:

[Hermitcraft Video Reference](https://www.youtube.com/watch?v=SSxgVNI-Ic4)

By confirming the builder and visual clues, I was able to match the interior shots to the correct coordinates.

---

### Step 4 – Advanced Assistance with BlockESP

For the **final screenshot**, I had exhausted visual and map-based clues. To confirm the exact location, I used **Doomsday Client** with the **BlockESP** feature to highlight blocks visible in the screenshot. This allowed me to precisely locate the in-game coordinates, even for tricky interior shots.

Website: [Doomsday Client](https://doomsdayclient.com/)

---

### TL;DR – Quick Steps

* Start with the **3D View Hermitcraft Map** to solve outdoor location screenshots
* Download Hermitcraft Season 6 map for local exploration of interiors
* Use **OSINT** to identify which player built certain structures
* Explore the world in Minecraft client to match screenshots
* For difficult shots, use **Doomsday Client** + BlockESP to identify exact block positions
* Record the coordinates for each screenshot and submit
