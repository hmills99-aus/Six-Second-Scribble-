# Six Second Scribble — putting it on people's phones

Everything here is one folder of plain files. Nothing to compile, nothing to pay for.

```
index.html              the game
manifest.webmanifest    name, icon and colours for the installed app
sw.js                   offline cache
icons/                  home screen icons
```

## Getting it online (about ten minutes)

You need it on an `https://` address — that's a hard requirement for offline mode
to work. GitHub Pages does this for free.

1. Make a free account at **github.com** if you haven't got one.
2. Click **New repository**. Name it something short like `scribble`.
   Set it to **Public**. Tick nothing else. Create it.
3. On the empty repository page, click **uploading an existing file**.
   Drag in `index.html`, `manifest.webmanifest`, `sw.js` **and the whole `icons`
   folder**. Scroll down, click **Commit changes**.
4. Go to **Settings** (top of the repo) → **Pages** (left sidebar).
   Under *Source* choose **Deploy from a branch**, pick **main** and **/ (root)**,
   then **Save**.
5. Wait a minute or two and refresh. GitHub shows you the address, which will be:

   `https://YOUR-USERNAME.github.io/scribble/`

That link is the app. Send it to anyone.

## Installing it on a phone

**Android / Chrome** — open the link. An *Install on this phone* button appears
under the rules; tap it. Chrome may also offer its own install banner.

**iPhone / Safari** — open the link, tap the **Share** button (the square with the
arrow), then **Add to Home Screen**. Safari doesn't allow an in-page install
button, which is why the app shows a reminder instead.

Either way it lands on the home screen with its own icon, opens with no browser
bar, and works with no signal after the first load. Good pubs have bad wifi.

## Handing it round at a party

Make a QR code pointing at your Pages link — search "QR code generator", paste the
URL, print it. Everyone points a camera at it and they're in.

## Changing anything later

Edit `index.html` (the word lists are three plain arrays near the top of the
`<script>` block), upload the new copy to the repo, **and change the version line
near the top of `sw.js`**:

```js
const CACHE = "scribble-v1";   →   const CACHE = "scribble-v2";
```

Skip that step and phones will happily serve the old cached version forever.

## A note on the app stores

This isn't in the App Store or Google Play, and doesn't need to be. Getting it
there means $99/year to Apple, and for Google a $25 one-off plus a closed test
with 12 testers opted in for 14 straight days before a new personal account can
publish. For a party game you hand round to friends, the home screen install
gets you the same result for nothing.
