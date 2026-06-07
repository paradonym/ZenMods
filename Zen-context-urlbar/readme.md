# Zen Context URL Bar

Adds URL bar access and shortcut hints to Zen Browser's right-click context menus. Inspired by the sidebar address bar's quick-access philosophy — bring the URL bar to your mouse pointer rather than your mouse to the URL bar.

## What this mod does

- **Toolbar right-click** – Shows a styled "URL Bar · Ctrl+L" hint at the top of the toolbar context menu, so you always have a reminder and visual cue that the URL bar is one shortcut away
- **Page right-click** (optional) – Same hint in the main content area context menu
- **Tab right-click** (optional) – Same hint in the tab context menu
- **Always-visible sidebar URL bar** (optional) – Keeps the sidebar address bar permanently visible in Single Toolbar mode, even in compact mode or when the top toolbar is hidden, bypassing the need to hover the sidebar edge

## Why CSS only?

Zen Mods are CSS-only by design — they inject into the browser's `userChrome.css`. A fully interactive address bar widget cannot be inserted into a context menu via CSS alone (the XUL DOM would need to be modified). What this mod does instead:

1. Adds a visual keyboard shortcut reminder at the top of context menus (`Ctrl+L` opens the URL bar in any layout)
2. Makes the existing sidebar URL bar always accessible without hover in single-toolbar / compact mode

## Preferences

Go to **Settings → Zen Mods → Zen Context URL Bar → ⚙️** to configure:

| Preference | Default | Effect |
|---|---|---|
| Show hint in toolbar right-click | ✅ On | Recommended — adds the hint to the toolbar context menu |
| Show hint in page right-click | Off | Adds hint to the main content area right-click |
| Show hint in tab right-click | Off | Adds hint to tab right-click menu |
| Always show sidebar URL bar | Off | Keeps the sidebar URL bar visible without hover (compact mode) |

## Compatibility

- Works with both **Single Toolbar** and **Multiple Toolbar** layouts
- Compatible with the **Zen Context Menu** mod — enable gradient/accent settings there and this mod adapts automatically
- Tested on Zen Browser (based on Firefox 128+)

## Known limitations

Due to CSS-only constraints, the hint is non-interactive (it's a visual label, not a clickable button). Click on the context menu background to dismiss and then press `Ctrl+L` to open the URL bar.

A fully clickable URL bar entry in context menus would require a JavaScript userscript or a browser extension, which is outside the scope of Zen Mods.

[Star the repo](https://github.com/paradonym/ZenMods/) if you find this useful!
