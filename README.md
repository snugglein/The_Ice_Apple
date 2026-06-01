# TheIceApple

A dark, editorial web experience built with React + TypeScript + Vite + Tailwind CSS + Framer Motion.

## Pages

- `/#/` — **Home** (Hero with video background, cycling roles, scroll indicator)
- `/#/about` — **About Us** (Floating 3D objects, scroll-driven character animation)
- `/#/stories` — **Stories** (Scroll-driven marquee rows of story cards)
- `/#/newsletter` — **Newsletter** (Sticky stacking issue cards with scale animation)

> Uses **HashRouter** — URLs look like `yoursite.com/#/about`.
> This means zero server config needed and zero 404 errors on any static host.

## Local Development

```bash
npm install
npm run dev
```

Visit: http://localhost:5173

## Deploy to Vercel (recommended)

1. Push folder to a GitHub repo
2. Go to vercel.com → New Project → Import repo
3. Framework preset: **Vite** (auto-detected)
4. Build command: `npm run build`
5. Output directory: `dist`
6. Click **Deploy** — done, no extra config needed

## Deploy to Netlify

1. Push folder to a GitHub repo
2. Go to netlify.com → Add new site → Import from Git
3. Build command: `npm run build`
4. Publish directory: `dist`
5. Click **Deploy** — done (`public/_redirects` handles any fallback)

## Deploy to GitHub Pages

1. Install: `npm install --save-dev gh-pages`
2. Add to `package.json` scripts:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   ```
3. Run: `npm run deploy`
4. In repo Settings → Pages → set source to `gh-pages` branch

## Why 404 happens & how this fixes it

On static hosts, going directly to `/about` returns 404 because there is
no actual `about.html` file — it is a React route. **HashRouter** puts the
route after a `#` in the URL (`/#/about`), which is never sent to the server,
so the server always serves `index.html` and React handles the rest.

## Tech Stack

- React 18 + TypeScript
- Vite 5
- Tailwind CSS 3
- Framer Motion 11
- React Router DOM 6 (HashRouter)
- Inter + Instrument Serif (Google Fonts)
