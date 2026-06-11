# Clothing templates (shirts & pants)

The avatar previewer loads **real shirt/pants art from local files you supply here.**
Nothing in this project fetches clothing assets from Roblox — those assets are gated
behind an authenticated session, and this tool deliberately does **not** handle Roblox
account credentials. You provide the template images yourself.

## How to add a shirt or pants

Drop a **585 × 559 PNG** (the classic Roblox clothing *template* — the flat, unwrapped
UV layout with the torso / arm / leg regions) into the matching folder, named by its
catalog asset ID:

```
avatar-data/clothes/shirt/<assetId>.png
avatar-data/clothes/pants/<assetId>.png
```

Example:

```
avatar-data/clothes/shirt/1804714.png
avatar-data/clothes/pants/1804739.png
```

The `<assetId>` must match the `id` of a `Shirt` / `Pants` entry in
`avatar-data/catalog.json` for it to light up in the picker.

## How the picker behaves

- The tool **auto-detects** which IDs have a file present (no manifest to maintain).
- A Shirt/Pants item **with** a local template here → selectable; clicking it maps the
  template onto the 3D body.
- A Shirt/Pants item **without** a local template → shown dimmed with a ↓ marker
  ("not downloaded"); selecting it just reverts to the blank template.
- You can always use the **upload** controls instead to drop in a one-off template
  without saving it here.

## Where to get the template images

Use a source where **you** are the one authenticated — e.g. export the template from
Roblox Studio (where you're signed in), or run your own asset-download tool and copy the
resulting 585×559 PNGs into these folders. The handling of any account credentials stays
entirely on your side, outside this project.
