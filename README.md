# bandithefirefly.com — how this site works

Hi Bandi. This is your site. Everything here is plain HTML files plus an `img` folder and a `video` folder. No framework, no build step. Change a file, commit it, and the live site updates by itself in a minute or two.

## How changes go live

```
you edit a file on GitHub  →  Cloudflare Pages notices  →  bandithefirefly.com updates
```

Nothing else is needed. You never have to log into Cloudflare.

To edit on GitHub: open the file → click the pencil icon (top right) → change things → green **Commit changes** button. To add an image: open the `img` folder → **Add file → Upload files**.

If you ever break something, don't panic. Every commit is saved. You can open the file's **History** on GitHub and restore an older version, or ask mom to hit "Rollback" in Cloudflare.

## Files

| file | what it is |
|---|---|
| `index.html` | home page: the island scene, the Sticks teaser, the Games lockers, the Seeds sky |
| `sticks.html` | the Sticks essay, in dialogue boxes |
| `seeds.html` | your idea journal, three tiers |
| `about.html` | placeholder — under construction sign. Yours to write. |
| `game-virus.html` | Error 404 (videogame version) |
| `game-board.html` | Error 404 (tabletop version) — includes all 54 tiles from `img/tiles/` |
| `game-vn.html` | Where Abandoned Ideas Go |
| `game-shooter.html` | Untitled First and Third Person Horror Game |
| `game-minigame.html` | Morning Routine |
| `img/` | all pictures. `img/tiles/1.jpg` … `54.jpg` are the board game tiles |
| `video/` | gameplay videos (mp4) |

Every page is self-contained: its CSS is inside the file in a `<style>` block at the top. There is no shared stylesheet, so if you change the look of one page and want it everywhere, you have to change it in each file (or ask for help making a shared `style.css` — that's a good first upgrade).

## The pieces you'll edit most

**Dialogue boxes** — the essay and all descriptions use this:

```html
<div class="say wob"><span class="who">Bandi</span>Your text goes here.</div>
```

Copy that whole line to add another box. `wob` is the wobbly-border effect; remove the word if you want a straight box.

**The big dialogue at the top of each page** (the visual-novel style one):

```html
<div class="textbox wob">Text here. <b>Bold part.</b></div>
```

**A locker on the home page** (in `index.html`, inside `<div class="lockers wob">`):

```html
<a class="locker" href="game-virus.html">
  <span class="num">01</span>
  <h3>Title</h3>
  <span class="meta">date · engine · role</span>
  <p>One or two sentences.</p>
  <span class="tag">in progress · video</span>
</a>
```

Order on the page = order in the file. Move the block to move the locker.

**The spec strip on a game page** (year / engine / team / my part / status):

```html
<div><span class="k">engine</span><br><span class="v">Unity · C#</span></div>
```

**A framed screenshot**:

```html
<figure class="frame wob" style="margin:0">
  <img class="wide" src="img/your-file.jpg" alt="describe the picture">
  <figcaption>caption in handwriting</figcaption>
</figure>
```

**The "What I learned" boxes** on every game page still say `(Bandi writes this part.)`. Those are waiting for you.

## Things that are placeholders right now

- `about.html` — only a sign. Needs: three sentences about you, a photo (or a drawing), a résumé link.
- Every "What I learned" box.
- Game pages say "video goes here" only in the preview copies; on the live site the videos play.
- The Seeds block on the home page says "11 ideas · 0 games · yet" and "+7 more in the drawer". Those numbers are typed by hand in `index.html`; update them when you add ideas to `seeds.html`.
- The Seeds page titles (Bow & Arrow, Fragments, Foreign Kitchen, The Scope, and the rest) were written by someone else as placeholders. Rename them.

## Style rules the site follows (break them on purpose if you want)

Black, white, one grey (`#EBEBEB`). Two fonts: Source Sans 3 for reading, Patrick Hand for handwriting (both from Google Fonts, linked at the top of each page). Borders are 2px black. The wobble comes from an SVG filter at the top of each page called `wobble`; it is applied only to the border of anything with class `wob` (via `.wob::before`), so the text inside stays sharp. Nothing has a shadow. Nothing is rounded.

## Adding a new game

1. Copy `game-minigame.html` (it's the simplest) to `game-newname.html`.
2. Change the `<title>`, the top dialogue, the spec strip, the text boxes, the images.
3. Add a locker for it in `index.html`. Put it first if it's the newest.
4. Put its pictures in `img/`, video in `video/` (keep videos under ~15 MB; re-encode if bigger).
5. Commit. Check the live site on your phone too.

## If you want to go further

- Install **GitHub Desktop** so you can edit locally and preview by opening the html file in a browser before pushing.
- Make a shared `style.css` and have every page `<link>` to it.
- Upload playable builds to itch.io and link them from the lockers.

The sign says under construction. It's supposed to.
