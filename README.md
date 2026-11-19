# Fishy Goes Fishing 🎣🐟

A reverse-fishing meme game: **you're the fish**, and you catch the humans.

Swimmers cross the surface — cast your net up, haul them in, and score before the 75-second timer runs out. Golden swimmers are worth bonus points, crabs pinch and snap your line, and dolphins give you a bonus when they pass.

## Play it

Open `index.html` in any browser, or host this repo with GitHub Pages (Settings → Pages → Deploy from branch → `main`) and play from the link.

- **Android / iPhone:** drag to move, tap **CAST NET**
- **PC:** mouse or arrow keys to move, **Space** to cast

Tap **Click to Start** first — browsers block sound until the first tap/click.

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
