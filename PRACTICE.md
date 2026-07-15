# Practice Guide

Repo: https://github.com/dwagnon/chatgpttesting

This repo is a safe sandbox for learning how Codex, local Git, and GitHub fit together.

## Mental Model

- GitHub is the remote home for the repository.
- Codex can use the GitHub connector to inspect repos, create files, create branches, and open pull requests.
- Local Git commands like `git commit`, `git push`, `git pull`, and `git merge` happen in a clone on your machine.
- A branch is an alternate line of work.
- A commit is a saved snapshot.
- A push sends local commits to GitHub.
- A pull fetches commits from GitHub and integrates them locally.
- A merge combines one branch into another.
- A pull request is a GitHub conversation around merging one branch into another.

## What Codex Is Doing Here

Codex seeded this repo through the GitHub connector. That means GitHub has real commits even though we did not run `git push` from your terminal.

Next, Codex can create a branch and open a pull request. You can inspect the PR visually on GitHub, compare files, comment, merge, or close it.

## Normal PR Practice

1. Create a branch from `main`.
2. Change `menu.txt`.
3. Commit the branch.
4. Open a pull request from the branch into `main`.
5. Review the diff on GitHub.
6. Merge the PR.

## Conflict Practice

A merge conflict happens when two branches change the same line differently.

For this repo, the conflict target is `homepage.txt`:

```text
Tagline: Calm coffee for careful commits.
```

One branch can change it to:

```text
Tagline: Bold coffee for brave branches.
```

Meanwhile `main` can change it to:

```text
Tagline: Friendly coffee for focused teams.
```

When the branch tries to merge back into `main`, GitHub or local Git will ask which final text should win.

A resolved version might be:

```text
Tagline: Friendly coffee for brave branches.
```

## Useful Local Commands

```powershell
git clone https://github.com/dwagnon/chatgpttesting.git
cd chatgpttesting
git status
git branch -a
git log --oneline --graph --decorate --all
```

Create and push a branch locally:

```powershell
git switch -c practice/my-change
# edit a file
git add .
git commit -m "Practice local change"
git push -u origin practice/my-change
```

Then open a pull request on GitHub, or ask Codex to open one for the pushed branch.
