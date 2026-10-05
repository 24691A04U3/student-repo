# Day 0 — Git & GitHub onboarding

🏢 **You are:** a brand-new analyst at FoodCo. Before you touch any data, you need to get onto the team's workflow. At FoodCo, all course materials and all your work live on **GitHub** — you receive new work by *pulling*, and you hand in work by opening a *Pull Request*. Today you set that up and make your first contribution.

## 📋 The scenario
It's your first hour. IT has given everyone access to the team's GitHub repo. Your onboarding buddy says: *"Fork it, clone it, add yourself to the team roster, and raise a PR. If your PR shows up, you're officially on the team."*

## ✅ Your task

Follow **[`GIT_WORKFLOW.md`](../GIT_WORKFLOW.md)** step by step:

1. **Configure Git** with your name and email.
2. **Fork** the course repo on GitHub.
3. **Clone your fork** to your laptop.
4. **Add the `upstream` remote** (the trainer's repo).
5. **Add yourself to the team roster:** create a file `roster/<yourname>.md` in this folder's structure with three lines:
   ```
   # Your Name
   - City you're in:
   - One thing you want to get out of this bootcamp:
   ```
6. **Commit** it on a branch, **push** to your fork, and **open a Pull Request** to the trainer's repo.

## ✔️ You're done when
Your Pull Request appears in the trainer's repo with your `roster/<yourname>.md` file in it. The trainer will merge it live so you can watch your change land in the official repo.

## 💡 Why this matters
This is not busywork — it's the actual daily loop for the next 10 days:
- **Every morning:** `git pull upstream main` to get the new day's folder.
- **End of each task:** commit → push → Pull Request to submit.

By Day 10 you'll do this without thinking — and "I know Git and GitHub" is a line that belongs on your résumé.

## 🏁 Today's Git commands (you'll use these all bootcamp)
```bash
git pull upstream main          # get new work
git checkout -b day00-yourname  # a branch for your work
git add roster/                 # stage your change
git commit -m "Add myself to the roster"
git push origin day00-yourname  # upload to your fork → then open the PR on GitHub
```
