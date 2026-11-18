# Rise in Office · Records of Notables

A browser board game rebuilt from *Sheng Guan Tu*, a traditional Chinese promotion-chart pastime. Players start as commoners, climb the fifteen ranks of the imperial examination system, and race to the Three Excellencies. Everything runs on plain HTML, CSS, and JavaScript — no build step, no framework, no server.

- Play (GitHub Pages): <https://luoluo926.github.io/sheng-guan-tu/>
- Mirror: <https://37k7pztvvw9neu47eoq.traesite.cn>

## What the game is

The original *Sheng Guan Tu* is a printed paper game from the Ming and Qing dynasties: a spiral of official titles, a spinning top, and a set of counters. This project keeps that structure and adds two layers on top — character-driven play and modern card mechanics.

Each match seats two to four players. On your turn you either play a hand card or skip and spin. The spinning top resolves on one of four faces: virtue (德), talent (才), merit (功), and graft (赃). Virtue jumps you up several ranks, talent advances you one, merit moves you a single step, and graft sends you back down. Cards intervene in that flow — they can re-roll an outcome, chain promotions, impeach a rival, or recommend an ally. The first player to reach the Three Excellencies wins; if the deck or the ranks run out first, final standing is decided by current rank.

## Modes

**Scholar** is the approachable mode. You pick one of eight commoner personas, each with a starting position and a passive trait, then play the promotion race.

**Notables** casts every seat as a historical figure from the Song, Ming, and Qing courts, each with their own ability tuned to a particular stage of the climb.

Both modes share the same board, deck, and resolution rules, so switching modes never changes what you already know about the game.

## Repository layout

```
index.html               Single-page build: markup, styles, and game logic in one file
index-standalone.html    Identical copy kept for offline distribution
data/
  config.json            Rule parameters, asset path templates, theme tokens, card copy
  content.json           Board cells, rank ladder, personas, decks, event pools
  lang.json              Runtime translation table (en / zh)
  lang-zh-cn.json        Simplified Chinese strings for nested UI fields
assets/
  bg/                    Scene backdrops
  board/                 Board art and overlay layers
  cards/                 Card faces, identity cards, card backs
  ui/  ui_v5/            Interface chrome, buttons, panels, ornaments
  loading/               Boot sequence frames
  ending/  end/          Ending illustrations and result screens
  fx/                    Particles and transition sprites
  audio/                 Music and sound effects (see assets/audio/CREDITS.md)
```

## How it is put together

The whole game is a single document. `index.html` carries the screens as sections — title, setup, game, collection, and ending — and switches between them by toggling classes rather than routing. Styles live in one stylesheet block, grouped by screen, so a change to the setup screen cannot leak into the board.

Layout is drawn on a fixed 1920×1080 canvas. A small script measures the window and applies a single `transform: scale()` to the canvas, which keeps every pixel position predictable across monitors and makes the mobile view the same composition at a smaller factor. Positioning inside the canvas is therefore always expressed in design coordinates, never in viewport pixels.

The game itself is data-driven. `data/config.json` holds tunable numbers — starting ranks, spin weights, promotion steps, drop pools — plus theme colors and asset path templates. `data/content.json` holds the board, the rank ladder, the persona roster, deck composition, and the event table. Changing a persona or rebalancing a face of the top is a data edit, not a code edit. Copy for cards and popups is read from the same config so artists and writers can iterate without touching logic.

Localization is handled at runtime. `data/lang.json` maps a source string to an English and a Chinese rendering, and a `MutationObserver` walks text nodes as screens render, translating anything it recognizes. The document carries `data-lang="en"` or `data-lang="zh"`, which lets CSS adjust font size, letter spacing, and line height per language — English labels are wider, Chinese labels are shorter, and the layout budgets for both. The two languages are kept strictly separate: the Chinese build contains no Latin abbreviations, and the English build contains no Chinese characters.

Rendering avoids a virtual DOM and re-renders each panel from state when it changes. That keeps the code readable at the scale of one file and makes debugging a matter of reading the current state object.

## Running locally

Any static server works:

```bash
python -m http.server 8000
```

Then open `http://127.0.0.1:8000/`. Opening `index.html` directly from disk also runs, though browsers restrict asset reads for local files, so the server route is preferred.

## Deployment

GitHub Pages serves the `release` branch directly. A push to that branch republishes the site within a minute; there is no build step, so what is committed is what ships. The same tree is also uploaded to a separate static host, and both addresses are listed at the top.

## Assets and licensing

Music and sound effects come from public-domain and permissively licensed sources; the exact origin and license for each file is recorded in `assets/audio/CREDITS.md`. Board art, card faces, and interface pieces were drawn for this project.

## Feedback

Bug reports and suggestions are welcome through the issue tracker.
