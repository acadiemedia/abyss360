# ChloeOS (ABYSS 360)

A self-contained first-person 360° underwater shark shooter. One `index.html` holds the game, renderer, custom Dev Studio, ambient life, weapon logic, and debug hooks. The `music/` folder bundles five CC0 tracks for forks that want an external soundtrack.

## Play

- Production: `https://<owner>.github.io/<repo>/`
- Branch preview: `https://<owner>.github.io/<repo>/preview/<sanitized-branch>/`
- Local: open `index.html` directly in a browser.

The game works from `file://`. The Incubator tab is the exception: it calls same-origin `/api/incubator/*` endpoints and is disabled on `file://`.

## What is inside

- 360° look with gyroscope/drag fallback.
- Tap to fire; hold the screen to open **CHLOEOS · DEV STUDIO**.
- Harpoon and speargun modes.
- Presets: `DEFAULT`, `FRENZY`, `CHILL`, `NIGHTMARE`.
- Harpoon builds: `WHALER`, `TESLA`, `DEMO`, `ANCHOR`.
- Live tuning for weapons, controls, combat, sharks, world, HUD, and audio.
- `COPY JSON` copies the current config to the clipboard.
- Runtime hooks: `window.__CHLOE_GAME__` and `window.__ABYSS__`.

Settings persist in `localStorage` under `chloeos_abyss360_cfg`. High score uses `abyss360_hi`.

## Repo layout

- `index.html` — the complete playable ChloeOS (ABYSS 360) game.
- `music/` — five CC0 OpenGameArt tracks.
- `LICENSE` — CC0-1.0 text.
- `THIRD-PARTY-NOTICES.md` — component provenance and license boundaries.
- `.github/workflows/preview.yml` — native-git GitHub Pages publisher.

## Vibe loop

1. Fork the repo on GitHub.
2. Make a branch: `vibe/<your-name>`, `fork/<idea>`, or `music/<track>`.
3. Edit `index.html` in GitHub's web editor, github.dev, or any local editor.
4. Push. The workflow publishes `preview/<sanitized-branch>/`.
5. Play the preview URL, tune again, and push again.
6. Open a pull request when the branch is worth merging into the shared root.

Branch structure is slime mold-like: one shared root, many thin exploratory branches, no central gatekeeper for experimentation.

## Publishing setup

1. Use this folder as the repo root on the default branch.
2. Push the default branch once so the workflow can create `gh-pages`.
3. In repository **Settings → Pages**, choose **Deploy from a branch**, then `gh-pages` / `root`.
4. Ensure workflow permissions allow `contents: write`.
5. After that, every push publishes automatically.

The workflow uses plain `git`, `tar`, and shell copying. It does not use third-party GitHub Actions.

## Local Incubator backend

The in-game Incubator expects these same-origin endpoints:

- `GET /api/incubator/health`
- `GET /api/incubator/forks`
- `POST /api/incubator/wish`
- `GET /api/incubator/fork/<id>`
- `DELETE /api/incubator/fork/<id>`

A static server such as `python3 -m http.server 8899` will serve the game but will not implement these APIs. The game banner references HTTP `:8899` or HTTPS `:8443`; providing those endpoints requires a backend.

## Safety

Live mods are executed with `new Function` through `CHLOE_API`. Only merge mod code from forks you trust. Generated Incubator code is just as executable as hand-written code.

## License

Original ChloeOS packaging and modifications are offered under CC0-1.0. Bundled music is CC0-1.0. Embedded Three.js/GLTFLoader is MIT. The embedded shark model and panorama have unknown provenance and are documented in `THIRD-PARTY-NOTICES.md`; they are not claimed as CC0.
