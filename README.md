# Image Sensor Explorer (v3.3.0)

One CMOS image sensor, followed from photons to bits: image quality, dynamic range, timing and parallelism.

`index.html` is the whole app: React and all code are inlined, and there are no external files, fonts or network calls. It runs entirely in the viewer's browser and nothing is sent anywhere.

## Put it on GitHub Pages

1. Create a new repository on GitHub, for example `image-sensor-explorer`. It must be public on a free account.
2. Upload `index.html` (and this README) to the root of the `main` branch: **Add file → Upload files → Commit**.
3. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**, then **Save**.
4. After a minute or two the site is live at
   `https://<your-user-name>.github.io/image-sensor-explorer/`
   Share that link.

To update the site, upload a new `index.html` over the old one. Pages redeploys automatically.

## Rebuild after changing `ImageSensorExplorer.jsx`

You need Node.js. In an empty folder:

```bash
npm init -y && npm i react@18 react-dom@18 esbuild
# put ImageSensorExplorer.jsx here, then create entry.jsx:
cat > entry.jsx <<'JS'
import { createRoot } from "react-dom/client";
import SensorExplorer from "./ImageSensorExplorer.jsx";
createRoot(document.getElementById("root")).render(<SensorExplorer />);
JS
npx esbuild entry.jsx --bundle --minify --format=iife --jsx=automatic \
  --define:process.env.NODE_ENV=\"production\" --target=es2018 --outfile=app.js
```

Then paste the contents of `app.js` into `index.html`, replacing everything between `<script>` and `</script>`. Or ask Claude to rebuild it.
