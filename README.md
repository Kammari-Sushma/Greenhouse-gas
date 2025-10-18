# Greenhouse Predictor — Frontend (Prototype)

This is an attractive, responsive static frontend built with Tailwind (via CDN) and vanilla JavaScript.
It is designed to plug into your existing Greenhouse Gas project quickly.

## What you get
- `index.html` — main UI (hero, quick predict form, CSV upload, results card and simple chart)
- `js/main.js` — form handling, demo mode, and instructions to update the API endpoint
- `README.md` — this file

## How to use
1. Download or copy the `index.html` and `js/main.js` files into your project or hosting folder.
2. Open `index.html` in a browser to try the demo UI.
3. To connect to your model, edit `js/main.js` and set `API_URL` to your prediction endpoint (e.g. `https://<your-host>/predict`).
   - The script expects a JSON POST and a response like:
     ```json
     { "prediction": 12.345, "model": "MyModel v1", "series": [12.3, 12.7, 13.0] }
     ```
   - Alternatively, keep `API_URL` as `/predict` and implement that route on your backend to receive the POST requests.
4. The UI accepts a CSV upload (it reads the first data row) — adapt `parseCSV` in `js/main.js` if your CSV has a different layout.

## Deployment
This is a static site — you can host it on GitHub Pages, Netlify, Vercel (static), or any static hosting provider.

## Design notes & next steps (suggestions I can implement)
- Replace Tailwind CDN with a proper Tailwind build for production.
- Add charts (Chart.js or Recharts) for richer visuals.
- Convert to React + Tailwind components if you want a component-driven app.
- Add authentication, file previews, and batch predictions for CSVs.

---

If you'd like, I can:
- Convert this into a React + Tailwind project with reusable components.
- Wire the UI directly to your Python model endpoint (if you provide the endpoint or allow me to add a small server file).
- Create deployment configuration for Vercel/Netlify.

Tell me which of the above you'd like next and I'll update the package. :)

# Greenhouse Predictor — Frontend (Updated)

This frontend is a responsive, attractive static UI (Tailwind CDN + vanilla JS) for the Greenhouse Gas project.

## Files
- `index.html` — main UI (hero, quick-predict form, CSV upload, results card and tiny trend chart)
- `js/main.js` — form handling, demo mode, CSV parsing and fallback demo behavior
- `README.md` — this file

## How to run
1. Put these files into your project directory (maintain `js/main.js` path).
2. Open `index.html` in a browser (double-click or right-click → Open With → Chrome/Edge).
3. Click **Use Demo Data** to see the UI working offline.
4. Or fill the form and click **Predict**.

## Connecting to your backend
- By default `js/main.js` uses `const API_URL = '/predict'`, which triggers demo behavior for offline testing.
- To connect to your model, edit `js/main.js` and set:
  ```js
  const API_URL = 'http://127.0.0.1:5000/predict';
