# Now or Next board

An interactive Spurgeons Now or Next board. Families drag cards onto **now** and **next**
(or tap a card, then tap where it goes), then save the board as a PDF or print it.

## How the page flows

1. **Intro** (opens first). The picture shows what's happening *now*; the little card shows what's *next*. Tap the picture to move on.
2. **How it works** (`#how`). A short demo plays itself, then the practice board becomes "your turn". Finishing the practice shows **Start now**.
3. **The board** (`#board`). The real board, the icon library and the request footer.

Returning visitors who have seen the demo get **Start now** as the main button on the intro. The browser back button moves between the screens.

## What's in the folder

```
index.html                 the whole page (styles and script included)
images/icons/              the 12 library illustrations (PNG, as supplied)
images/logo/               official Spurgeons logos (Main, Full and Shorthand)
images/illustrations/      online.svg, the animated picture in the request footer
```

## Put it on GitHub Pages

1. Create a repository and upload everything in this folder, keeping the `images` folder next to `index.html`.
2. In the repository go to **Settings → Pages**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
3. The board will be live at `https://<your-org>.github.io/<repo-name>/` after a minute or two.

Saving as PDF works best from the live link. If you open `index.html` straight from your computer,
the browser blocks the PDF builder, so the page opens the print window instead (choose **Save as PDF** there).

## Set where icon requests go

The request form sits in the navy footer at the bottom of the page.

Near the top of the `<script>` in `index.html`:

```js
const CONFIG = {
  iconRequestEmail: "",   // e.g. "design@spurgeons.org" — requests open as an email to this inbox
  iconRequestGithub: ""   // optional: "https://github.com/<org>/<repo>/issues/new" — requests open as a GitHub issue
};
```

If both are empty, the request opens in the person's email app with no recipient filled in.

## Add a new icon to the library

1. Save the PNG (transparent background, square, about 1080px) into `images/icons/`.
2. Add a line to the `ICONS` list in `index.html`:

```js
{id:"bath", label:"bath time", src:"images/icons/bath.png", tint:"purple"},
```

`tint` is the card colour: `purple`, `red` or `yellow`.

## Good to know

- Boards and home-made cards are saved in the visitor's own browser only. Nothing is uploaded.
- Up to three now-and-next pairs per board. One pair saves as a landscape A4 PDF; two or three save as portrait.
- Follows the visitor's light or dark setting. Animations switch off for anyone who has reduced motion turned on.
- Fonts (Outfit, Figtree) load from Google Fonts and the PDF builder (jsPDF) from cdnjs.
