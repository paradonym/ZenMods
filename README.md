# THIS IS AI! Untested work in Progress. Used Model:  Perplexity Computer work time approx. 6 minutes.

Human comment: In the end all it does is that there are visual clues to Ctrl+L in the context menu, instead of a fully functional context menu address bar.

## ZenMods by paradonym

Zen Browser mods. See individual mod folders for details.

## Mods

- **[Zen Context URL Bar](Zen-context-urlbar/)** – Adds URL bar shortcut hints and always-visible sidebar URL bar controls to Zen's right-click context menus.


## AI Explaination output

### What the mod does
Since Zen Mods are CSS-only (they inject into userChrome.css, no JS), a fully interactive URL bar inside a context menu is not possible — Firefox's XUL context menu can't host live input widgets via CSS. Instead, the mod takes the most useful approach possible:

Toolbar right-click (default on): shows a styled "URL Bar · Ctrl+L" chip at the top of the menu — same visual language as the sidebar address bar, acts as a persistent shortcut reminder

Page/Tab right-click (optional): same hint in other menus

Always-visible sidebar URL bar (optional): keeps the compact sidebar address bar permanently shown in single-toolbar/compact mode, bypassing the need to hover the top edge — this is the feature closest to "bringing the sidebar address bar to you"

### How to test it locally
#### Method 1 — Direct file install (fastest for testing):

Open Zen Browser → go to about:support

Click "Open Profile Folder" next to "Profile Directory"

Navigate to the chrome/ subfolder (create it if missing)

Open or create userChrome.css and add at the top:

css
@import url("chrome://userchrome/content/zen-context-urlbar.css");
Or simply paste the contents of chrome.css directly into userChrome.css.

Make sure toolkit.legacyUserProfileCustomizations.stylesheets is set to true in about:config

Restart Zen Browser

Right-click the toolbar — you should see the URL bar hint at the top

#### Method 2 — Load as a local Zen Mod:

Go to Settings → Zen Mods → Load from file (if that option exists in your Zen version)

Point it at theme.json from the repo

#### Method 3 — Test via about:config toggles:
Once the CSS is active, open about:config and set these booleans to toggle features:

Pref	Effect
uc.urlbar-in-context.show-kbd-hint	Hint in toolbar right-click
uc.urlbar-in-context.show-in-page-menu	Hint in page right-click
uc.urlbar-in-context.show-in-tabmenu	Hint in tab right-click
uc.urlbar-in-context.float-sidebar-urlbar	Always-visible sidebar URL bar
You don't need to restart — @media -moz-pref() toggles are live.

### How to publish to the Zen Theme Store
Add a real screenshot (image.png, must be PNG) — replace the placeholder in the repo. A screenshot of the context menu with the hint bar visible is ideal.

Submit via GitHub Issue on zen-browser/theme-store with:

Name: Zen Context URL Bar

Description: Adds URL bar shortcut hints and sidebar URL bar access to right-click context menus

Homepage: https://github.com/paradonym/ZenMods/

Image: URL to your image.png (e.g. upload to Imgur first)

CSS: paste the contents of chrome.css (without any @-moz-document wrapper)

Preferences: paste preferences.json contents

Readme: paste readme.md contents

A bot will create a PR automatically. A maintainer reviews it and merges it into the store. Once merged, the mod appears in the Zen Mods store at zen-browser.app/mods/ecc5d5c9-d118-4374-8c81-b7e61fabaad0.

One honest caveat: The mod uses ::before pseudo-elements and CSS custom properties to inject the UI — this works well for the visual hint. If you want a truly clickable menu item that fires Ctrl+L, that would require either a Zen Desktop PR (to add a native XUL menuitem to toolbarContextMenu) or a Firefox extension. That's worth a feature request on the zen-browser/desktop discussions if you want to take it further.
