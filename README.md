# Fishy Goes Fishing 🎣🐟

An **open-world, character-POV** reverse-fishing meme game: you're a fish who grew **human legs**, roaming a big world and catching humans in different places. The camera rides behind and above Fishy like a 3D .io game, so the **whole avatar is always visible** in the foreground while the world stretches ahead of him in perspective — horizon, sky, and the four places with their signs on the horizon.

## The world

A 2,600 × 1,800 world with a camera that follows you, and four places to hunt:

- **Sunny Beach**
- **Wooden Pier**
- **Splash Pool**
- **River Delta** — golden humans hide by the river

## .io-style interface

Like a 3D fishing .io game: a live **leaderboard** with rival players, a **minimap** showing the whole world and every human, a current-place banner, score/combos, and depth-sorted pseudo-3D rendering. You have 90 seconds per round.

## Play it

**Live:** https://taoshif007-cpu.github.io/fishy-goes-fishing/

Or open `index.html` in any browser. Tap **Click to Start** first — browsers block sound until the first tap/click.

- **Android / iPhone:** on-screen joystick to walk, tap **CAST NET**
- **PC:** WASD to walk the way Fishy is facing, drag or ←/→ to swing the camera/turn, **Space** to cast

## Missions & avatars

Tap the 🎯 **Missions** button to see live progress. Mission progress tracks across rounds within a play session.

- **Golden Hunter** — hunt 20 ★ Special golden humans → unlock the **Golden Fishy** avatar (crown + glow)
- **Human Hunter** — 50 total catches → unlock **Shark Fishy**
- **World Explorer** — visit all 4 places → +1,000 pts
- **Combo King** — catch ×5 in one net → unlock **Rainbow Fishy**

Special humans are gold, labelled ★ SPECIAL, and shown as gold dots on the minimap. Unlocking an avatar auto-equips it with a fanfare; switch avatars any time from the Missions panel or the start screen.

## Meme sound effects — all generated in code

No audio files. Every sound is synthesized live with the **Web Audio API**, and the silly voice lines use **speechSynthesis**. All sounds live in one `sounds` object in `index.html`, one function per sound:

- **Caught:** boing/bonk, airhorn (3+ humans in one net), ka-ching bonus, random voice lines — *"Oh no!", "Not again!", "Help me!", "Why me?"*
- **Escaped:** sad trombone, evil cartoon laugh, record scratch when the line snaps, dancing voice lines — *"Nice try, fishy!", "Too slow!", "Hahaha!"*
- **Other:** crab pinch squeak/honk, dolphin chirp, game-over *"dun dun dunnn"*
- Mute button + volume slider included

### Swap any sound for your own .mp3

At the top of the `sounds` object in `index.html` there's a comment showing exactly where. Replace that sound's function body with:

```js
playFile("assets/your-sound.mp3");
```

and drop your file in an `assets/` folder.
