# gwq-gc 🧹💅

[English](README.md) | **日本語**

[gwq](https://github.com/d-kuro/gwq) で作った worktree のうち、マージ済みで未コミットの変更が無いやつをまとめて消しちゃうコマンドだよ💖🧼✨

既定は dry-run で、`--apply` を付けたときだけ `gwq remove -b` を実行するよ🙆‍♀️  
リモートブランチは消さないから安心してね🫶

## 🛍️ 必要なもの

- bash
- git
- gwq

## 📦 導入

```sh
install -m 755 gwq-gc ~/.local/bin/gwq-gc
```

## 🎀 使い方

```sh
gwq-gc                        # dry-run (今いるリポジトリ)
gwq-gc --apply                # 確認してから削除
gwq-gc --apply -y             # 確認せずに削除
gwq-gc --squash-ok            # squash マージされたものも候補にする
gwq-gc --base origin/develop  # 比較するブランチを指定
gwq-gc --no-fetch             # fetch しない
```

マージ済みかどうかは、既定だとブランチの先端が比較先の祖先かどうかで決めるよ🌳  
比較先を指定しなければ、`origin/HEAD`、`origin/main`、`origin/develop` の順に探すよ。

## 📜 ライセンス

MIT 💖
