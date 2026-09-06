# GNN-BERT Music Context — Listening Study

A human evaluation page for the **GNN-Based BERT for Understanding Context from Music** project (CSE425, BRACU).

---

## What this is

This is a **static, self-contained listening study webpage** used to collect human perceptual ratings for AI-generated music descriptions.

Participants are presented with 24 numbered music clips (~10 seconds each). For each clip they:

1. Read an AI-generated natural-language description produced by the GNN-BERT model.
2. Listen to the audio clip using the in-page player.
3. Rate on a 1–5 scale how well the description matches what they hear.

Ratings are collected via a **separate external form** (e.g., Google Forms) referenced in the study instructions — not through this page.

---

## Technical details

| Property | Value |
|---|---|
| Type | Pure static HTML |
| Dependencies | **None** — zero external scripts, fonts, or stylesheets |
| Audio delivery | 24 MP3 clips embedded as base64 `data:` URIs |
| JavaScript | None |
| Backend required | No |
| File size | ~32 MB (due to embedded audio) |

---

## Running locally

No build step or server is required. Simply open the file in any modern browser:

```bash
# Option 1 — double-click
# Open index.html directly in your browser (File → Open or drag-and-drop)

# Option 2 — local HTTP server (avoids any browser restrictions on large data URIs)
python -m http.server 8000
# Then visit http://localhost:8000
```

> **Note:** Most browsers handle the page fine when opened directly. If audio does not play, use a local HTTP server.

---

## Deploying to GitHub Pages

1. Create a new GitHub repository (public or private with Pages enabled).

2. Push the contents of this folder:

   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial deploy: GNN-BERT listening study"
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```

3. In the repository on GitHub, go to **Settings → Pages**.

4. Under **Source**, select **Deploy from a branch** → `main` → `/ (root)`.

5. Click **Save**. GitHub will provide a public URL such as:

   ```
   https://<your-username>.github.io/<your-repo>/
   ```

---

## Notes

- Do **not** extract or host the audio files separately unless you also rewrite the `src` attributes in `index.html`.
- The page is fully functional offline once loaded — all audio is embedded.
- No cookies, tracking, or analytics are present.
