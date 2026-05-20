# Deploy The Muscle Bee Fitness to Vercel (via GitHub)

This project is **static HTML** at the repository root (`index.html` + assets). Vercel serves it with no build step.

## Files prepared for Vercel

| File | Purpose |
|------|--------|
| `index.html` | Main site (entry URL `/`) |
| `gym.png` | Logo & favicon — **must be committed** |
| `*.html` | Redirect stubs → anchors on `index.html` |
| `vercel.json` | `cleanUrls` / `trailingSlash` (optional polish) |
| `.gitignore` | Keeps junk out of Git |

No `package.json` is required. Vercel will detect a static site.

---

## Part 1 — GitHub (push your code)

### 1. Install Git (if needed)

Download: [https://git-scm.com/downloads](https://git-scm.com/downloads)

### 2. Create an empty repository on GitHub

1. Log in to [GitHub](https://github.com).
2. **New repository** (green button or **+** → **New repository**).
3. Name it (e.g. `muscle-bee-fitness`).
4. Choose **Public** (or Private — Vercel supports both on paid plans; free tier works with private on Pro or use Public).
5. **Do not** add README / .gitignore / license (you already have files locally), or you’ll get a merge conflict — create an **empty** repo.
6. Copy the repo URL, e.g. `https://github.com/YOUR_USERNAME/muscle-bee-fitness.git`

### 3. In your project folder (`c:\gym`)

Open **PowerShell** or **Terminal** in `c:\gym` and run:

```powershell
cd c:\gym
git init
git add .
git status
```

Confirm **`gym.png`** appears in the list. If it’s missing, add the file to this folder before committing.

```powershell
git commit -m "Add Muscle Bee Fitness static site for Vercel"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

If GitHub shows **authentication** errors, use a **Personal Access Token** as the password (GitHub → Settings → Developer settings → Personal access tokens), or sign in with **GitHub CLI** (`gh auth login`).

---

## Part 2 — Vercel (deploy from GitHub)

### 1. Sign up / log in

Go to [https://vercel.com](https://vercel.com) and sign in with **GitHub**.

### 2. Import the repository

1. Vercel Dashboard → **Add New…** → **Project**.
2. **Import** your `muscle-bee-fitness` (or whatever you named it) repository.
3. Configure the project:
   - **Framework Preset:** Other (or “Other” / no framework — Vercel may show “Other” for static sites).
   - **Root Directory:** `./` (leave default — repository root).
   - **Build Command:** leave **empty** (not required).
   - **Output Directory:** leave **empty** or default (not required for plain HTML at root).

### 3. Deploy

Click **Deploy**. After ~30–60 seconds you get a URL like `https://your-project.vercel.app`.

### 4. Custom domain (optional)

Vercel project → **Settings** → **Domains** → add `themusclebeefitness.com` (or your domain) and follow DNS instructions from your registrar.

---

## Part 3 — After each change

```powershell
cd c:\gym
git add .
git commit -m "Describe your change"
git push
```

Vercel **auto-deploys** on every push to `main` (default). Other branches can get **Preview** deployments if enabled in the project settings.

---

## Troubleshooting

| Issue | What to do |
|--------|------------|
| Site shows 404 | Ensure `index.html` is at the **root** of the repo (same level as `vercel.json`). |
| Logo broken | Commit `gym.png` in the repo root; paths are relative (`gym.png`). |
| Old page cached | Hard refresh (Ctrl+F5) or Vercel → Redeploy. |
| `git push` rejected | If you created the repo with a README on GitHub, run `git pull origin main --allow-unrelated-histories`, resolve, then push — or start with an **empty** repo as recommended. |

---

## CLI alternative (optional)

If you use [Vercel CLI](https://vercel.com/docs/cli):

```powershell
npm i -g vercel
cd c:\gym
vercel
```

Follow prompts to link the folder to a Vercel project. For production: `vercel --prod`.

GitHub integration is still recommended for automatic deploys on push.
