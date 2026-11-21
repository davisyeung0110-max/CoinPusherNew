# 浣熊推幣機 · Raccoon Coin Pusher

### 深夜街機廳裡的 3D 推幣 Roguelike

**▶ [Play in your browser](https://davisyeung0110-max.github.io/CoinPusherNew/)**  
No install, no account, no backend. Desktop and mobile.

> 先投幣，再煩惱。  
> *Insert coin first. Worry later.*

---

## What is this?

A 15-round coin-pusher roguelike. Drop coins onto a physical 3D table, push the coin bed
toward the payout slot, build combos, spin the wheel, and spend your tickets in the shop
before the next shift starts. Reach the KPI before the 95-second timer runs out — or get
fired by a raccoon in a necktie.

The machine, coins, textures, mascot and UI are generated procedurally. There are no external
images, fonts, music or 3D models.

## Play

Open the link above, click **開始新班 / Start New Shift**, choose a character and difficulty,
then press **打卡上班 / Clock In**.

The first visit shows a short employee-handbook tutorial.

## Controls

| Action | Input |
| --- | --- |
| Drop a coin | `Space`, click the table, or drag and release |
| Switch left / right chute | `A` / `D` or the L/R buttons |
| Use a gift | `1` – `5` |
| Toggle camera | `C` |
| Shake the table when coins are stuck | `T` |
| Emergency coin exchange | `E` |
| Pause / close the current window | `P` / `Esc` |
| Restart the run | `R` (asks for confirmation) |
| Shop and binder | Mouse / touch |

## How a run works

1. Reach the **score target** shown at the top before the 95-second round ends.
2. Coins that cross the front edge fall into the payout slot, giving score, tickets and combo.
3. Every 10 combo points raise your score multiplier. The chain resets after a few seconds
   without a settlement.
4. After a successful round, spend tickets in the shop on coins, gifts, chips, plating,
   binder space or a coin supply crate.
5. Clear all 15 rounds to reach **Victory**, then continue into **Endless Overtime**.
   Miss a target and the run ends.

Useful details:

- The table starts with an **80-coin house bed** so the pusher always has something to push.
- Player coins wait in a short feed queue while the pusher is extended; the launch hint shows
  how many are waiting.
- The **Lucky Wheel** charges as coins settle. Spin it and push the pink gift ball into the
  payout slot to collect a gift. If your gift slots are full, it becomes tickets.
- Purple/green **bad coins** appear from round 3. They cost score and tickets and can taint
  nearby coins; clear them with coin effects or gifts.
- Progress saves automatically in `localStorage`. **Continue** appears on the main menu after
  a reload.
- On weaker GPUs or mobile, enable **Low Quality** in Settings for a smoother frame rate.

## Features

- Full 3D coin-pusher table with Rapier physics, composite pusher colliders and a dense coin bed
- 15 rounds, 8 difficulty tiers, endless mode after victory
- 30 playable coins plus locked codex placeholders; every effect is data-driven
- 22 gifts, 16 passive chips, 8 coin coatings
- 6 characters with unique passives and starting binders
- Shop, binder upgrades, plating selection, emergency exchange, table shake
- Combo multiplier, Lucky Wheel, gift balls, bad coins, gadgets and run summaries
- Seeded RNG, automatic saves, versioned save migration
- Procedural Canvas textures, SVG icons, WebAudio-synthesised sound effects
- Responsive desktop and mobile HUD; touch controls and drawers on narrow screens
- No backend, tracking, external assets or network requests after load

## Tech

- TypeScript (strict)
- Vite + React 18
- Three.js / React Three Fiber / drei
- `@react-three/rapier` physics
- Zustand state store
- Vitest unit tests
- WebAudio synthesis
- `localStorage` saves
- GitHub Pages static hosting

## Repository contents

This Pages repository currently contains the **compiled static build**:

```text
index.html
assets/
  index-*.js
  index-*.css
```

The playable site is served directly from these files. No build step or server is required
at runtime.

## Development

From the full source project:

```bash
npm install
npm run dev
```

```bash
npm run build      # typecheck + production build
npm run preview
npm run test       # Vitest
npm run lint
```

The Vite config uses a relative `base`, so the same build works at a GitHub project subpath,
a custom domain, Cloudflare Pages or local preview.

## Known limitations

- Art is intentionally procedural low-poly; there are no imported GLB characters or machines.
- Simplified Chinese UI is available, but most coin/gift/chip descriptions fall back to
  Traditional Chinese.
- No background music; all sound is synthesised at runtime.
- Very old devices without WebGL cannot run the game.
- Performance depends on the GPU; integrated graphics may prefer Low Quality.

## Credits

Game code, procedural geometry, Canvas textures, SVG artwork and synthesised audio were made
for this project. Open-source library licences belong to their respective authors; see the
source project's lockfile and package metadata.

---

**▶ [Play Raccoon Coin Pusher](https://davisyeung0110-max.github.io/CoinPusherNew/)**
