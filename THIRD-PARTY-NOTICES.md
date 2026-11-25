# Third-Party Notices — ChloeOS (ABYSS 360)

This file records what is known, inferred, and unknown about bundled components. Unknown provenance is not treated as permission.

## Original project material

- Project: ChloeOS (ABYSS 360)
- Packaging, scaffolding, and ChloeOS-specific changes: CC0-1.0, see `LICENSE`.
- This notice does not relicense third-party components.

## Three.js

- Component: embedded Three.js core.
- Location: `index.html:126-136`.
- License marker: `Copyright 2010-2021 Three.js Authors`, `SPDX-License-Identifier: MIT`.
- Revision marker: r128.
- Status: MIT; license marker preserved in the embedded source.

## GLTFLoader

- Component: embedded `GLTFLoader extends THREE.Loader`.
- Location: `index.html:137-3768`.
- Origin: Three.js r128 examples.
- License: MIT, inherited from Three.js r128.
- Status: MIT; embedded alongside the Three.js core.

## Shark glTF binary

- Component: embedded `SHARK_GLB` constant decoded at runtime.
- SHA-256: `2ecdb4aeba5a9425e12508150f07f50b5d532e511a2385185b7c1eaa59cf80ac`
- Extracted size: `97276` bytes.
- Embedded asset metadata: `{"generator":"Khronos glTF Blender I/O v0.9.2","version":"2.0"}`
- Scene data: 1 scene, 13 nodes, animations `bite` and `swim`, materials `Material.001` through `Material.004`.
- Author/copyright/license metadata: none found.
- Status: provenance unknown. Do not claim CC0. A web search surfaced a differently sized CC BY shark model, but that was not treated as proof of identity or licensing.

## Panorama

- Component: embedded `PANO` data URI used as the 360° dome texture.
- SHA-256: `ade787b049cb166e09322b0919c9cb222f427b91d90ebebe6cb64e364c395871`
- Extracted size: `546241` bytes.
- Format: JPEG, `2048x1024`, `codec_name=mjpeg`.
- EXIF/IPTC metadata: none returned by `exiftool`.
- Status: provenance unknown. Do not claim CC0.

## Bundled music

All five tracks were downloaded from OpenGameArt pages listing CC0.

- `music/abyss_360_deep_dive.mp3`
  - Source: `https://opengameart.org/content/deep-dive-0`
  - Direct file: `https://opengameart.org/sites/default/files/deepdive_0.mp3`
  - Duration: `179.017143`
  - License: CC0

- `music/abyss_360_thalassophobia.mp3`
  - Source: `https://opengameart.org/content/music-water-ambience`
  - Direct file: `https://opengameart.org/sites/default/files/thalassophobia.mp3`
  - Duration: `58.096327`
  - License: CC0

- `music/abyss_360_aquaria.wav`
  - Source: `https://opengameart.org/content/aquaria`
  - Direct file: `https://opengameart.org/sites/default/files/TylerSong3_Normal.wav`
  - Duration: `43.961179`
  - License: CC0

- `music/abyss_360_ambient_pad.ogg`
  - Source: `https://opengameart.org/content/underwater-ambient-pad`
  - Direct file: `https://opengameart.org/sites/default/files/Underwater-Ambient-Pad-isaiah658_0.ogg`
  - Duration: `16.671927`
  - License: CC0

- `music/abyss_360_drifting.ogg`
  - Source: `https://opengameart.org/content/drifting-0`
  - Direct file: `https://opengameart.org/sites/default/files/drifting_0.ogg`
  - Duration: `95.997098`
  - License: CC0

The music files are bundled but not automatically loaded by `index.html`; the current game uses synthesized WebAudio.

## Runtime mod execution

ChloeOS (ABYSS 360) exposes `CHLOE_API`, `applyMod`, and `window.__ABYSS__`. Mod code may be executed with `new Function`. This is a runtime capability, not a license grant for any embedded asset.
