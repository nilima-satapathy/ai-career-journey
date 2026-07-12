# GitHub workflow — how I track milestones

Use this every time you finish a milestone. Takes ~5 minutes. Keeps profile clean and honest.

---

## One-time setup (already done if repos exist)

| Repo | Purpose | Public? |
|------|---------|---------|
| `satnil2608-glitch` | Profile README (shows on your GitHub home) | Yes |
| `ai-career-journey` | Dashboard + PROGRESS.md | Yes |
| `api-automation-pytest` | Project 1 code | Yes |
| later: P2, P3, P4 | One repo per project | Yes |

**Pin on profile** (GitHub → profile → Customize pins):  
1. `ai-career-journey`  
2. `api-automation-pytest`  
3. (add others as you create them)

---

## Every milestone (copy-paste)

Replace `X` with the number (3, 4, …) and the message.

### 1) In the project folder

```powershell
cd C:\Users\admin\OneDrive\Desktop\Code\api-automation-pytest
.\.venv\Scripts\Activate.ps1
pytest
```

All green? Continue.

### 2) Update project milestone log

Edit `MILESTONES.md` → mark Done + today’s date.

### 3) Commit + tag + push

```powershell
git add -A
git status
git commit -m "feat(mX): short description of what you shipped"
git tag -a milestone-X -m "Project 1 Milestone X complete"
git push origin main
git push origin milestone-X
```

### 4) Update the journey dashboard

```powershell
cd C:\Users\admin\OneDrive\Desktop\Code\ai-career-journey
```

- Tick the box in `PROGRESS.md`  
- Update the status table in `README.md` if needed  
- Add a line under Weekly notes  

```powershell
git add -A
git commit -m "docs: log Project 1 milestone X"
git push origin main
```

### 5) Optional — GitHub Release (looks great on profile activity)

```powershell
cd C:\Users\admin\OneDrive\Desktop\Code\api-automation-pytest
gh release create milestone-X --title "Milestone X — short title" --notes "What shipped: ..."
```

---

## Commit message style (simple rules)

| Prefix | When |
|--------|------|
| `feat(m3):` | New milestone feature |
| `fix:` | Bug fix |
| `docs:` | README / PROGRESS only |
| `test:` | Tests only |
| `ci:` | GitHub Actions |

Examples:

- `feat(m2): add shared api_client fixture`  
- `feat(m3): parametrize user GET tests`  
- `docs: mark M3 complete in PROGRESS`

---

## Branching (keep it simple for now)

- Work on `main` for portfolio projects (solo learning).  
- Later, if you want PR practice: `git checkout -b feat/m3-parametrize` → PR → merge.

---

## What NOT to commit

- `.venv/`, API keys, `.env`, HTML reports with secrets  
- Already covered in each project’s `.gitignore`

---

## Profile checklist (do once this week)

- [ ] Profile name / bio updated  
- [ ] Profile README visible (repo `satnil2608-glitch`)  
- [ ] Pins set (journey + project 1)  
- [ ] LinkedIn GitHub link points here  
- [ ] Resume GitHub URL = `https://github.com/satnil2608-glitch`
