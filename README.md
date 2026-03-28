# Portfolio Setup Guide — Jihad Hasan Jony

## Step 1 — Organize your files

Create a folder on your PC, name it anything e.g. `jony-portfolio`. Put everything inside it like this:

```
jony-portfolio/
├── index.html                   ← rename jony-portfolio.html to this
├── JONY.pdf                     ← your CV file (already named correctly)
├── hero.jpg                     ← hero photo (corridor, black shirt)
├── about.jpg                    ← about photo (library, sitting)
└── README.md                    ← this file (optional, can delete)
```

> **Important:** The two image paths in the HTML still point to `/mnt/user-data/uploads/...` from when it was built. Before deploying, open `index.html` in a text editor (Notepad++, VS Code, anything) and do a Find & Replace:
>
> Find: `/mnt/user-data/uploads/`  
> Replace with: *(leave blank / empty string)*
>
> That turns the paths into just `IMG-20260318-WA0002.jpg` — which will work once they're in the same folder.

---

## Step 2 — Push to GitHub

You need [Git](https://git-scm.com/downloads) installed. Then open a terminal inside your `jony-portfolio` folder:

```bash
git init
git add .
git commit -m "first commit"
```

Go to [github.com](https://github.com), create a new repository (call it `jony-portfolio`, set it to **Public**). Then back in your terminal:

```bash
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/jony-portfolio.git
git branch -M main
git push -u origin main
```

---

## Step 3 — Deploy on Netlify

1. Go to [netlify.com](https://netlify.com) → sign up or log in (can use GitHub account)
2. Click **"Add new site"** → **"Import an existing project"**
3. Choose **GitHub** → authorize → select your `jony-portfolio` repo
4. On the build settings page — **leave everything blank** (no build command, no publish directory)
5. Click **"Deploy site"**

Netlify will give you a random URL like `https://sparkly-fox-123.netlify.app`.

To change it to something nicer:
- Go to **Site configuration → Domain management → Options → Edit site name**
- Set it to e.g. `jonyportfolio` → becomes `https://jonyportfolio.netlify.app`

---

## Step 4 — Future updates

Whenever you want to change something on the site:

1. Edit the files locally
2. Run in terminal:

```bash
git add .
git commit -m "describe what you changed"
git push
```

Netlify auto-redeploys within ~30 seconds.

---

## Quick reference — what each file does

| File | Purpose |
|---|---|
| `index.html` | The entire portfolio — all sections, styles, and JS in one file |
| `JONY.pdf` | CV — linked by the Download CV buttons |
| `IMG-20260318-WA0002.jpg` | Hero section photo |
| `IMG-20260318-WA0003.jpg` | About section photo |

---

## If something looks broken

| Problem | Fix |
|---|---|
| Images not showing | Did you do the Find & Replace in Step 1? |
| CV download not working | Make sure `JONY.pdf` is in the same folder as `index.html` |
| Site not updating after push | Go to Netlify dashboard → Deploys → check for errors |
| Toggle not working locally | Open via a local server, not by double-clicking the file. Use VS Code Live Server extension, or run `npx serve .` in the folder |
