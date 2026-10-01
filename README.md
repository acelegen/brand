# Acelegen brand assets

The one place for Acelegen's logo files. Sites and apps take the logo from here instead of keeping their own copies, so a logo change is made once.

## Files

| File | What it is | Use it for |
| --- | --- | --- |
| `mark/acelegen-mark.svg` | The Acelegen mark (circle and "a"), black, vector | Websites on a light background; recolour by using it as a CSS mask |
| `mark/acelegen-mark-white.svg` | The same mark, white, vector | Websites on a dark background |
| `mark/acelegen-mark-black.png` | Master artwork, black on transparent, 1041 × 952 | Documents, slides, anything that needs a bitmap |
| `mark/acelegen-mark-white.png` | Master artwork, white on transparent, 1041 × 952 | The same, on dark backgrounds |
| `app-icon/acelegen-app-icon-512.png` | White mark on teal `#0B5563`, rounded square, 512 × 512 | Favicons, app and launcher icons |
| `app-icon/apple-touch-icon-180.png` | The same on a full square, 180 × 180 | `apple-touch-icon` for websites |
| `wordmark/acelegen-wordmark-navy.png` | "ACELEGEN" lettering, navy `#17284F` on transparent, 1904 × 185 | Headers next to or instead of the mark, light background |
| `wordmark/acelegen-wordmark-light.png` | The same lettering, `#E8EBF2` on transparent | Dark background |

The outer ring of the mark is a hairline. Below about 40 px it stops reading as a ring, so use the app icon, not the bare mark, at favicon sizes.

The SVGs were traced from the master PNG: every difference is within one pixel of an edge at the master's size. When a designer's original vector exists, replace both SVGs with it.

## Use from a website

Load files through jsDelivr with the major version, so sites pick up new releases without a code change:

```html
<link rel="icon" type="image/png" href="https://cdn.jsdelivr.net/gh/acelegen/brand@1/app-icon/acelegen-app-icon-512.png" />
<link rel="apple-touch-icon" href="https://cdn.jsdelivr.net/gh/acelegen/brand@1/app-icon/apple-touch-icon-180.png" />
<img src="https://cdn.jsdelivr.net/gh/acelegen/brand@1/mark/acelegen-mark.svg" alt="Acelegen" height="40" />
```

- `@1` resolves to the newest `v1.x.y` tag. jsDelivr caches these version-range URLs for up to 7 days, so a new release can take that long to reach every site unless the cache is purged (jsDelivr's purge API; see their README).
- An exact version such as `@1.0.0` never changes. Use it where a logo must not move.
- jsDelivr keeps every file it has served permanently, even if it is later deleted here. Only commit finished, approved artwork.

## Use from an app

Launcher icons and other bundled resources cannot load from a URL. Copy the file from here into the app when the logo changes, and note the brand version in the commit message.

## Change the logo

1. Replace the files, keeping their names and sizes.
2. Commit and tag a new version: a new major version (`v2.0.0`) if sites should not pick it up automatically, otherwise a minor one (`v1.1.0`).
3. `git push origin main --tags`.

## Colours in use

These are the colours products use today. They are not yet one palette; agree on one before adding new uses.

| Where | Colours |
| --- | --- |
| acelegen.com and the internal site | navy `#17284F`, blue `#2C47E0`, paper `#F4F1EA`, ink `#1B1813` |
| App icon | teal `#0B5563`, white |

## Trademark

© Acelegen. The Acelegen name and logos are trademarks of Acelegen. This repository is public so that Acelegen's own sites and apps can load these files. It does not grant anyone else a licence to use them.
