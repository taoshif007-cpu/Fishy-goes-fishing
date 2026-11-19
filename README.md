# Fishy Goes Fishing 🎣🐟

An **open-world** reverse-fishing meme game with a classic **RPG overhead camera**: you're a fish who grew **human legs**, roaming a big world and catching humans in different places. The camera sits above the world and follows Fishy — the whole avatar visible at normal character scale — as he walks between the eight places.

## The world

A big open world (5,200 wide) with a camera that rides behind Fishy, and **eight places** to hunt:

- **Sunny Beach** · **Wooden Pier** · **Splash Pool** · **River Delta**
- **Jungle Trail** — tall grass, ferns, palms and rocks, like a jungle clearing
- **Waterfall Cove** — rocks, a waterfall and mist
- **Fishing Village** — huts, market stalls, fences and lamps
- **Coral Lagoon** — bright shallow water, coral, shells and boats

**Where the maps separate:** every boundary is detailed — wooden log gates and bridges at the crossings, signposts with the place name, torches, fence lines, stepping stones, border rocks and bushes, and a blended dirt-track strip in the ground. The place banner fires as you cross.

## .io-style interface

Like a 3D fishing .io game: a live **leaderboard** with rival players, a **minimap** showing the whole world and every human, a current-place banner, score/combos, and depth-sorted pseudo-3D rendering. You have 90 seconds per round.

## Play it

**Live:** https://taoshif007-cpu.github.io/fishy-goes-fishing/

Or open `index.html` in any browser. Tap **Click to Start** first — browsers block sound until the first tap/click.

- **Android / iPhone:** on-screen joystick to walk, tap **CAST NET**
- **PC:** WASD / arrow keys to walk, drag to walk towards the pointer, **Space** to cast

## Missions & avatars

Tap the 🎯 **Missions** button to see live progress. Mission progress tracks across rounds within a play session.

- **Golden Hunter** — hunt 20 ★ Special golden humans → unlock the **Golden Fishy** avatar (crown + glow)
- **Human Hunter** — 50 total catches → unlock **Shark Fishy**
- **World Explorer** — visit all 8 places → +1,000 pts
- **Combo King** — catch ×5 in one net → unlock **Rainbow Fishy**
- **Beach Hunter** — catch 25 humans at Sunny Beach → unlock **Explorer Fishy** (safari hat)
- **Pier Master** — catch 25 at Wooden Pier → unlock **Pirate Fishy** (pirate hat + eye patch)
- **Pool Party** — catch 25 at Splash Pool → unlock **Party Fishy** (party hat + sunglasses)
- **Delta Hunter** — catch 25 at River Delta → unlock **Jungle Fishy** (leaf camouflage)
- **Airhorn King** — trigger the airhorn 5 times → unlock **King Fishy** (big crown + cape)
- **Dolphin Friend** — meet the dolphin 5 times → unlock **Angel Fishy** (halo + wings)
- **Crab Dodger** — finish a round with no crab pinch → unlock **Ninja Fishy** (headband)
- **High Scorer** — score 5,000 in one round → unlock **Robot Fishy** (metal body + antenna)

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
## New: fishermen, health and dancing escapers

- **Fishermen** with rods and hooks wander the maps. They follow Fishy when he
  comes near, and inside their red hook-range circle they cast a hook at him:
  a hit costs **20 health**. Fishy has a health bar — dolphins heal +10, and
  at 0 health the round ends early. Net a fisherman to tangle him up.
- **Escaped humans dance and mock**: any human who escapes stops for a
  2-second dance with a mocking bubble ("Nice try, fishy!", "Too slow!",
  "Nyah nyah!") and a mocking laugh, then runs off at triple speed.

## Sounds

Real recordings, not computer voices — there is **no text-to-speech anywhere**
in this game; all funny lines appear as on-screen speech bubbles. The game
first tries to play the real CC0 (public-domain) recordings in the `sounds/`
folder (see `sounds/CREDITS.md`) and falls back to built-in synthesized
versions if a file is missing. To use your own meme sounds, replace any file
in `sounds/` keeping the same name: `boing.mp3`, `airhorn.mp3`,
`kaching.mp3`, `sad-trombone.mp3`, `record-scratch.mp3`, `evil-laugh.mp3`,
`mock-laugh.mp3`, `squeak.mp3`, `dolphin.mp3`, `game-over.mp3`, `hurt.mp3`.
