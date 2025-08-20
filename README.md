# HyperTap – HTML5 One‑Touch Game Template

A lightweight, reskinnable, hyper‑casual game built with pure HTML5 Canvas + JavaScript. Perfect for selling on CodeCanyon/Codester/SellMyApp or deploying as a web game with Adsterra/Ad networks.

## Features
- One‑touch gameplay (tap/click/space)
- Three difficulties (Easy / Normal / Hard)
- Clean code, no external libraries
- Responsive canvas, mobile‑friendly
- Sound effects (no assets needed)
- Local storage high score
- Ad hooks (banner/interstitial placeholder)
- Simple **CONFIG** block for reskinning

## File Structure
```
/HyperTap-GameTemplate
  ├── index.html
  ├── styles.css
  ├── game.js
  └── assets/       (put your logos, sprites, sounds here if needed)
```

## How to Run
Just open `index.html` in a browser. For best results, use a local server:
- VS Code "Live Server" extension, or
- Python: `python -m http.server 8000` and open `http://localhost:8000`

## Reskin & Settings
Open `game.js` and edit the `CONFIG` object at the top:
```js
const CONFIG = {
  gameTitle: 'YourGame',
  colors: { bg:'#000', player:'#22d3ee', obstacle:'#f43f5e', particle:'#fde68a', text:'#fff' },
  player: { radius: 18, gravity: 1650, jumpForce: 560, x: 120 },
  obstacle: { width: 46, gapMin: 120, gapMax: 200, spacing: 320, speed: 220 },
  difficulty: { easy:{...}, normal:{...}, hard:{...} },
  interstitialEvery: 3
};
```
- Change `gameTitle` (also updates the UI title)
- Tweak colors, sizes, speeds, gaps
- Set how frequently interstitial ads appear (`interstitialEvery`)

## Monetization (Adsterra / Others)

### Web (HTML5) – Banners/Social Bar/PopUnder
1. Create an Ad Unit in your ad network (e.g., Adsterra).
2. In `index.html`, replace the placeholder inside `#ad-slot` with the ad script the network provides (e.g., Social Bar/banner).
3. For lightweight interstitial, in `game.js` the function `maybeShowInterstitial()` injects content into `#ad-slot` after every N gameovers. Replace the placeholder with your interstitial script or open a custom modal that contains your ad.

> ⚠️ Always follow the ad network policies (e.g., no accidental clicks, frequency capping).

### Android/iOS (Optional via WebView wrapper)
- Wrap this HTML5 game into an Android WebView (Android Studio) or use a wrapper like Cordova/Capacitor.
- Use **AdMob/Unity Ads** natively in the wrapper and trigger interstitials on `Game Over` events (bridge JS <-> native).

## Packaging for Marketplaces
- Include:
  - `index.html`, `styles.css`, `game.js`, `assets/`
  - A `README.md` (this file) and `LICENSE.txt`
  - 3–5 high‑quality screenshots (desktop & mobile)
  - A short gameplay GIF (10–15s)
- Provide a **Reskin Guide** (below) and **Change Log**.

## Reskin Guide
1. Update colors & title in `CONFIG`.
2. Replace brand text in `index.html` (`.brand` + title in menu).
3. Add your logo in `/assets` and place it in the menu if desired.
4. Adjust obstacle sizes/gaps to change difficulty feel.
5. Edit CSS for font/rounded style.
6. Rename game to something catchy: *Tap Escape*, *Gap Dash*, *Sky Bounce*.

## Versioning & Change Log
- v1.0.0 – Initial release

## License
This template uses the MIT License (included). You can sell **licenses** to use/modify the code. You cannot resell this template **as-is** on other marketplaces without adding value (screens, features, assets), per most marketplace policies. Check your chosen marketplace terms.

## Support
For buyers, provide a short FAQ:
- *How to change colors?* – Edit `CONFIG.colors` in `game.js`.
- *How to change difficulty?* – Edit `CONFIG.difficulty` values or default selection in `index.html`.
- *How to add ads?* – Replace `#ad-slot` code and `maybeShowInterstitial()` with your ad network code.
