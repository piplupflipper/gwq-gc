# gwq-gc

[gwq](https://github.com/d-kuro/gwq) で作った worktree のうち、マージ済みで未コミットの変更が無いものを一括で削除するコマンドです。

既定は dry-run で、`--apply` を付けたときだけ `gwq remove -b` を実行します。
リモートブランチは削除しません。

## 必要なもの

- bash
- git
- gwq

## 導入

```sh
install -m 755 gwq-gc ~/.local/bin/gwq-gc
```

## 使い方

```sh
gwq-gc                        # dry-run (今いるリポジトリ)
gwq-gc --apply                # 確認してから削除
gwq-gc --apply -y             # 確認せずに削除
gwq-gc --squash-ok            # squash マージされたものも候補にする
gwq-gc --base origin/develop  # 比較するブランチを指定
gwq-gc --no-fetch             # fetch しない
```

マージの判定は、既定ではブランチの先端が比較先の祖先かどうかで行います。
比較先の既定は `origin/HEAD`、`origin/main`、`origin/develop` の順に探します。

## ライセンス

MIT
