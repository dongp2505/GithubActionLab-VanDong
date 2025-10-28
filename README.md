"# GithubActionLab-VanDong" 
## Workflows

### 1) Workflow 1 – Dependent Jobs (`dependent-jobs.yml`)
**Concepts:** `needs`, sequential jobs, basic steps  
**Flow:** `build → test → deploy` (each with ≥2 steps)

### 2) Workflow 2 – Env & Secrets (`env-and-secrets.yml`)
**Concepts:** env scopes (workflow, job, step), GitHub Secrets  
**Trigger:** Manual (`workflow_dispatch`)  
**Secrets used:** `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`  
**Note:** Secret values are masked in logs.

### 3) Workflow 3 – Multi-Platform (`multi-platform.yml`)
**Concepts:** parallel jobs, `runs-on` matrix of OSes  
**Trigger:** Pull Request to `main`  
**Jobs:** `ubuntu-latest`, `windows-latest`, `macos-latest`

## How to Run
- **Workflow 1:** push to `main`  
- **Workflow 2:** Actions → select the workflow → “Run workflow”  
- **Workflow 3:** open a PR to `main` from a feature branch

## Challenges & Resolutions
- *Secrets not found:* added under **Settings → Secrets and variables → Actions**.  
- *Workflow didn’t trigger:* checked `on:` filters and made a new commit to the right branch.  
- *Windows shell differences:* used `shell: cmd` for `systeminfo` and `type`.