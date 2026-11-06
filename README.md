# gwq-gc 🧹💅

**English** | [日本語](README.ja.md)

This command bulk-deletes the worktrees you made with [gwq](https://github.com/d-kuro/gwq) that are already merged and have no uncommitted changes 💖🧼✨

By default it's a dry-run, and it only runs `gwq remove -b` when you add `--apply` 🙆‍♀️  
It never deletes remote branches, so don't worry 🫶

## 🛍️ Requirements

- bash
- git
- gwq

## 📦 Install

```sh
install -m 755 gwq-gc ~/.local/bin/gwq-gc
```

## 🎀 Usage

```sh
gwq-gc                        # dry-run (the repo you're in)
gwq-gc --apply                # delete after asking
gwq-gc --apply -y             # delete without asking
gwq-gc --squash-ok            # also treat squash-merged ones as candidates
gwq-gc --base origin/develop  # pick the branch to compare against
gwq-gc --no-fetch             # don't fetch
```

By default, a branch counts as merged when its tip is an ancestor of the comparison branch 🌳  
If you don't pick one, it looks for `origin/HEAD`, `origin/main`, then `origin/develop`, in that order.

## 📜 License

MIT 💖
