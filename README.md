# R-Labs — Production Build

A ready-to-deploy production bundle of the R-Labs digital agency website.
This is a static site served by a tiny Node.js (Express) server, perfect for
Hostinger's Node.js hosting.

## What's inside

```
r-labs-deploy/
├── public/         # Pre-built static site (HTML, CSS, JS, images)
├── server.js       # Tiny Express server that serves the public/ folder
├── package.json    # Dependencies and start script
└── README.md       # This file
```

## Deploy on Hostinger (Node.js hosting)

1. **Upload the folder.** Upload everything in this folder to your Hostinger
   site directory (e.g. `public_html` or the directory your Node.js app
   points to). You can upload the ZIP and extract it from the File Manager.

2. **Set the application root.** In Hostinger's Node.js panel:
   - **Application root:** the folder you just uploaded (e.g. `r-labs-site`).
   - **Application startup file:** `server.js`
   - **Node.js version:** 18 or higher.

3. **Install dependencies.** From Hostinger's panel click **Run NPM Install**,
   or from SSH:
   ```bash
   cd ~/your-app-folder
   npm install
   ```

4. **Start the app.** Click **Start App** in the Hostinger Node.js panel.
   Hostinger will set the `PORT` environment variable automatically and
   route your domain to it.

5. **Done.** Open your domain — the R-Labs site will be live.

## Run locally (optional)

```bash
npm install
npm start
# open http://localhost:3000
```

You can override the port with the `PORT` environment variable:
```bash
PORT=8080 npm start
```

## Notes

- This is a fully self-contained build. No external API or database required.
- All assets (images, fonts, CSS, JS) are bundled inside `public/`.
- The server enables gzip compression and SPA-style routing
  (any unknown URL falls back to `index.html`).
