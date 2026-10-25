# Browser dashboard

This static site is a results viewer for the generated `output.csv`. It shows
case totals, status filters, search, and each case's ordered audit steps. It
does not run the Python audit or connect to live customer systems.

## Preview locally

From this directory, start any static file server. For example:

```powershell
py -m http.server 8000
```

Then open <http://localhost:8000>. If `py` is unavailable, install Python 3.12
and enable **Add Python to PATH** in its installer.

## Deploy to Vercel

1. Push the project to a GitHub repository.
2. In Vercel, choose **Add New → Project** and import that repository.
3. In project settings, set **Root Directory** to `web`.
4. Leave the framework preset as **Other**. Leave Build Command and Output
   Directory empty (or use `.` for Output Directory).
5. Select **Deploy**. Vercel serves `index.html` and `output.csv` as static files.

The dashboard loads `output.csv` beside `index.html`. After regenerating the
audit results, copy the new root-level `output.csv` into this `web` directory
and redeploy so the website reflects the updated results.

## Deploy with Vercel CLI

Install Node.js, open PowerShell in this directory, then run:

```powershell
npx vercel
```

Follow the prompts to sign in and deploy. Use `npx vercel --prod` when ready
to publish to production.
