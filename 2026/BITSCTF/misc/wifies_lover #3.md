# Wifies_Lover #3

> *"The ocean was chosen because it looks infinite. Somewhere beyond the horizon lies a future drop location, not transmitted directly, only implied. The Resistance left behind a tool called CoolCommand, but its manual was lost during the evacuation. No instructions. No explanation. Only the name remains. Those who use it notice change, but not chaos. Don't Lose Hope, even wrong steps are steps towards a goal."*

This challenge is the third in the Wifies_Lover series. To reach this world, I needed the coordinates from **Wifies_Lover #2**, which involved cryptography. Since I did not solve that problem, I asked a teammate for the coordinates so I could continue the exploration.

Upon teleporting to the third world, the description proved accurate. The world was almost entirely ocean, and there were no obvious clues. I initially spent some time stuck, unsure how to proceed. 

![Ocean](https://i.imgur.com/lqPNlZ3.png)

Re-reading the problem description highlighted the hint about **CoolCommand**, which “leaves change, but not chaos.” This suggested that experimentation with this tool was required.

After investigating the server commands, I found there were only two relevant commands: `/guess` for submitting coordinates and `/coolcommandplugin:cool_command`. Running the CoolCommand killed the player immediately, but it subtly modified the spawnpoint.
![Killed](https://i.imgur.com/yPpkQ40.png)
By repeatedly executing the command, I observed that my spawnpoint was confined to a small region around approximately **x: 6749 z: 2465**.

![Limit](https://i.imgur.com/3CIcuFl.png)

Focusing on this area, I explored the ocean floor and noticed something unusual. Among the uniform gravel seabed, a single **Suspicious Gravel** block stood out. Its distinct appearance suggested it was the intended clue for the problem.

Using this observation, I executed `/guess` directly above the Suspicious Gravel block. This action successfully revealed the flag:

```
BITSCTF{L0_S13nt0_W1ls0n}
```

![Flag](https://i.imgur.com/f5E1p5n.png)

---

### Takeaway

This challenge was enjoyable because it relied on **careful observation and experimentation** rather than explicit hints. The CoolCommand initially seemed lethal, but repeated use revealed subtle mechanics affecting the spawnpoint. 

---

### TL;DR – Quick Steps

* Teleport to Wifies_Lover #3 using coordinates from #2
* Explore the ocean world and realize there are no obvious clues
* Discover that `/coolcommandplugin:cool_command` subtly shifts your spawnpoint
* Spam the command to restrict your exploration area (around x: 6749 z: 2465)
* Scan the ocean floor and find a **Suspicious_Gravel** block
* Submit `/guess` directly above the block
* Receive the flag: `BITSCTF{L0_S13nt0_W1ls0n}`


