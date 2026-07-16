# YouTube Grid Layout Changer

> A lightweight Chrome extension that keeps YouTube's video grid responsive and consistent.

## Installation

1. Open Chrome and go to `chrome://extensions/`.
2. Enable **Developer mode** in the top-right corner.
3. Click **Load unpacked**.
4. Select this extension's folder.
5. Open or refresh YouTube.

## What it does

The extension controls both parts of YouTube's home-page layout:

- The loaded video grid, using YouTube's `--ytd-rich-grid-items-per-row` variable.
- The separate loading-placeholder layout shown before videos appear.

Both layouts use the same responsive column count, so loading cards no longer change size or reflow when the videos finish loading.

### Responsive layout

| Screen width | Items per row |
| --- | ---: |
| Up to 767px | 1 |
| 768px-1023px | 2 |
| 1024px-1365px | 3 |
| 1366px and above | 4 |

The layout updates automatically when the browser window is resized or moved between displays.

## Customization

Edit `styles.css` to change the breakpoints or column counts. The shared `--ytgc-items-per-row` variable controls both loaded videos and loading placeholders.

For example, add these rules after the existing media queries to use five and six columns on wider displays:

```css
@media (min-width: 1600px) {
    :root {
        --ytgc-items-per-row: 5;
    }
}

@media (min-width: 1920px) {
    :root {
        --ytgc-items-per-row: 6;
    }
}
```

To use a fixed number of columns at every screen size, remove the media queries and change the default value:

```css
:root {
    --ytgc-items-per-row: 4;
}
```

After editing the CSS:

1. Save `styles.css`.
2. Open `chrome://extensions/`.
3. Click the reload button for this extension.
4. Hard-refresh YouTube with `Ctrl+Shift+R`.

## Files

| File | Description |
| --- | --- |
| `manifest.json` | Chrome extension configuration |
| `styles.css` | Loaded-grid and loading-placeholder layout rules |
| `assets/icon*.png` | Extension icons |
| `README.md` | Installation and customization guide |

## License

Free to use and modify.
