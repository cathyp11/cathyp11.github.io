# GitHub Actions Setup — One-time steps

After pushing this workflow, do these two things in the GitHub repo settings:

## 1. Add repository secret

`Settings → Secrets and variables → Actions → New repository secret`

- **Name**: `RISKREPORT_PASSWORD`
- **Value**: `yejinpark2026` (or whatever password you want)

Only you (repo owner) can read this. It's used by the workflow to encrypt riskreport pages.

## 2. Change Pages source

`Settings → Pages → Build and deployment`

- **Source**: change from `Deploy from a branch` → **`GitHub Actions`**

That's it. Push to `main` triggers the workflow, which builds Jekyll and encrypts riskreport pages before deploying.

## Updating the password later

Just change the `RISKREPORT_PASSWORD` secret value. Next deploy will use the new password.

## Everyday editing

Edit `riskreport.html` and `riskreport-kr.html` at repo root normally (they have Jekyll front matter). Commit and push — the workflow re-encrypts them automatically.
