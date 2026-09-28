# 32 Hackney Pony Lane – Nearby Places Map

An interactive map for the listing page. It shows the drive time and distance from the home to nearby places. Visitors can:

- click a place (on the map or in the list) to see its drive time, distance and a **Get directions** link
- turn on **📏 Measure** and tap anywhere to see how far that spot is from the home
- use it on a phone: the list turns into a swipeable strip under the map

Everything is in one file, `index.html`. No build step and no API key.

## Editing places

Open `index.html` and edit the `CONFIG` block near the top of the `<script>`. For each place you can set:
`name`, `category`, `emoji`, `address`, `lat`/`lng`, `drive` (minutes) and an optional `photo` URL.

### Fixing marker positions

The coordinates are close but approximate. To make them exact:

1. Open the page with `?edit=1` added to the URL (for example `index.html?edit=1`).
2. Drag each marker to its exact spot.
3. Copy the coordinates from the box in the corner into `CONFIG`.

## Embedding on the listing site

**Option A – host it, then embed with an iframe (recommended)**

1. Host `index.html` somewhere public. The simplest way is GitHub Pages for this repo: Settings → Pages → deploy from the branch. Netlify Drop also works.
2. In the site builder, add an **Embed / Custom HTML** block and paste:

```html
<iframe src="https://YOUR-HOSTED-URL/index.html"
        style="width:100%;height:600px;border:0;border-radius:12px"
        loading="lazy" title="Nearby places map"></iframe>
```

**Option B – paste the whole file**

If the builder's custom-HTML block accepts full pages or scripts, you can paste the contents of `index.html` straight into it.
