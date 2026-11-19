# Fishy Goes Fishing 🎣🐟

An **open-world** reverse-fishing meme game: you're a fish who grew **human legs**, roaming a big world and catching humans in different places.

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
- **PC:** WASD / arrow keys to walk, **Space** to cast, or drag with the mouse

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
