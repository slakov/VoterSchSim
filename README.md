# RIG Opinion Dynamics Dashboard

Single-file interactive dashboard for simulating opinion dynamics on a Random Intersection Graph (RIG), combining:
- Schelling-style structural adaptation (group leaving/joining)
- Voter-model state updates (opinion adoption)

Live app is published via GitHub Pages.

## Repository Info
- Repository: `https://github.com/slakov/VoterSchSim`
- Git remote (`origin`): `https://github.com/slakov/VoterSchSim.git`
- Default branch: `main`
- Main app file: `index.html`

## Live Deployment
- Expected GitHub Pages URL: `https://slakov.github.io/VoterSchSim/`
- Deployment model: push changes to `main` (or your configured Pages source), GitHub Pages republishes.

## Local Run
No build step is required.

Option 1:
- Open `index.html` directly in a browser.

Option 2 (recommended for consistent behavior):
```bash
python3 -m http.server 8080
```
Then open: `http://localhost:8080`

## Update and Push New Versions
Use this flow whenever you update the dashboard:

```bash
# 1) Sync
git pull --ff-only origin main

# 2) Edit files (typically index.html and README.md)

# 3) Commit
git add index.html README.md
git commit -m "Update simulation dashboard"

# 4) Push
git push origin main
```

After push, GitHub Pages should update automatically.

## One-Time Remote Setup (Only If Needed)
If `origin` is ever missing:

```bash
git remote add origin https://github.com/slakov/VoterSchSim.git
git branch -M main
git push -u origin main
```

## Model Notes
- **Initialization** (`n`, `m`, `p`, initial ratio) applies on **Reset**.
- **Leaving rate** is base intensity; effective leave probability is scaled by minority pressure inside each group.
- **Modes**:
  - `Schelling-only`: structural updates only
  - `Voter-only`: opinion updates only
  - `Combined`: both per simulation step

## File Structure
- `index.html`: full app (HTML, CSS, JS inline)
- `README.md`: project and deployment guide
