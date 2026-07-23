# AR Model Placement (WebXR Hit Test)

Based on the official immersive-web/webxr-samples "hit-test" demo, with the sample
sunflower swapped for your model at `media/gltf/mymodel/model.glb`.

## Folder structure
```
sunflower-ar/
├── index.html              <- the AR page (open this on your phone)
├── css/
│   └── common.css
├── js/
│   ├── render/              <- rendering engine (do not touch)
│   └── util/                <- WebXR button helper (do not touch)
└── media/
    └── gltf/
        ├── mymodel/
        │   └── model.glb    <- YOUR model. To update later, replace this file.
        └── reticle/
            └── (placement marker files, do not touch)
```

## Uploading to GitHub (from Desktop/Paperad)

1. Move the whole `sunflower-ar` folder into `Desktop/Paperad/`, so you have
   `Desktop/Paperad/sunflower-ar/`.
2. On github.com, create a new empty repository (no README, no .gitignore,
   no license) — name it e.g. `sunflower-ar`.
3. Open the `sunflower-ar` folder in VS Code, open a terminal, and run:
   ```
   git init
   git add .
   git commit -m "Initial AR project"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/sunflower-ar.git
   git push -u origin main
   ```
4. On the repo page: Settings → Pages → Source: "Deploy from a branch",
   Branch: `main`, folder: `/root` → Save.
5. Wait about a minute. Your live link will be:
   ```
   https://YOUR-USERNAME.github.io/sunflower-ar/
   ```
   Put THIS link in your QR code.

## Updating the model later

To change the model without changing the link/QR code:
1. Replace `media/gltf/mymodel/model.glb` with the new file (keep the same filename).
2. In VS Code terminal, inside the folder:
   ```
   git add .
   git commit -m "Update model"
   git push
   ```
3. Refresh the page on your phone — same link, new model.

## Testing on Android

- Use **Chrome** (not Samsung Internet or others).
- Make sure "Google Play Services for AR" is installed (Chrome will prompt if missing).
- Open your GitHub Pages link, tap "START AR", allow camera access, point at a
  flat, well-lit surface, tap to place. Walk around — placed objects stay put.

## If the model looks huge, tiny, sideways, or floating

That means the model's own scale/origin from your 3D software doesn't match
real-world meters. Tell me and I'll add a scale/rotation fix to the code —
this is a one-line change, not a rebuild.

## iPhone

This WebXR method does not work on iPhone (Safari/WebKit don't support it,
regardless of browser used). A separate fallback page for iPhone (using Apple's
AR Quick Look) can be added on request.
