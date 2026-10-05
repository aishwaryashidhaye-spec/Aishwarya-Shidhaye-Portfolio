# Aishwarya Shidhaye: portfolio

React + Vite + Tailwind. One extra dependency (react-router-dom).

## Run locally
```
npm install
npm run dev        # http://localhost:5173
npm run build      # outputs /dist
npm run preview    # test the production build
```

## Deploy on Netlify
1. Push this folder to a GitHub repository.
2. Netlify: Add new site, Import from Git, pick the repo.
3. Build command `npm run build`, publish directory `dist` (already set in `netlify.toml`, which also adds the SPA redirect `/* /index.html 200`).
4. Deploy. No environment variables are needed.
5. After you have a domain, replace `https://YOUR-DOMAIN.netlify.app` in `index.html` (canonical, og:url, og:image, twitter:image).

## Photographs
Put files in `public/images/` with the names listed in `public/images/README.md`. To change names or add more, edit the `images` and `behindTheScenes` blocks in `src/data/portfolioData.js`. Missing images never break the site.

## Add a project
Open `src/data/portfolioData.js` and add one object to the array for the role you held:
`directorWork`, `writerWork`, `creativeDirectorWork`, `assistantDirectorWork`, `otherWork`, `actingWork`.
Fields: `id, title, category, role, type, description, url, linkType, status, featured`.
- Several pieces under one project: set `url: null` and add `links: [{label, url, linkType}]`.
- Not released yet: `status: 'coming-soon'`, `url: null`, `linkType: 'none'`.
- Show on the home page: `featured: true`.
The Work page, filters and home page all read from this file; nothing else needs editing.
If you worked on a project in two roles, add it to both arrays (as Chiraag is).

## Notes on external media
YouTube thumbnails are loaded from YouTube for links that are YouTube videos. Instagram, Drive and Docs open as clearly labelled external links. Film posters are not downloaded or hotlinked; cards are typographic until you add licensed poster files.
