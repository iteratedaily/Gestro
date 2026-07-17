# Gestro

A local-first Chrome extension for hands-free navigation of short-form video using simple hand gestures.

Gestro lets you control YouTube Shorts, Instagram Reels, and TikTok with a webcam. No mouse, no keyboard, no tracking.

## Overview

- 1 finger → next / scroll down
- 2 fingers → previous / scroll up
- 3 fingers → toggle speed
- 4 fingers → pause / resume
- 5 fingers → quit extension

Gestro processes video frames locally using MediaPipe Hands and maps recognized gestures to platform controls.

## Install

```bash
git clone https://github.com/IterateDaily/Gestro.git
cd gestro
npm install
npm run build
```

`npm run build` runs `npm run download-models` automatically through the `prebuild` hook.

## Load in Chrome

1. Open `chrome://extensions/`
2. Enable **Developer Mode**
3. Click **Load unpacked**
4. Select the `dist/` folder

## Usage

1. Open a supported video page.
2. Enable Gestro in the popup.
3. Allow camera access.
4. Hold your hand palm-facing the camera.
5. The HUD shows when the extension is listening.

## Supported Platforms

- YouTube Shorts
- Instagram Reels
- TikTok

## Developer

```bash
npm run dev
npm run build
npm run test:accuracy
```

## Project structure

```
gestro/
├── src/
│   ├── background/
│   ├── content/
│   │   ├── camera.ts
│   │   ├── hud.ts
│   │   ├── logger.ts
│   │   ├── mediapipe.ts
│   │   ├── recognizer.ts
│   │   ├── state-machine.ts
│   │   └── platforms/
│   └── popup/
├── scripts/
│   ├── build.ts
│   └── download-models.ts
├── icons/
├── models/hands/
├── manifest.json
└── package.json
```

## Privacy

- Camera feed is processed locally and discarded
- No accounts, analytics, or telemetry
- Audio is disabled
- Only the enabled state is stored

## Requirements

- Node.js ≥ 18
- npm ≥ 9
- Chrome ≥ 120

## License

MIT. See [LICENSE](LICENSE).
