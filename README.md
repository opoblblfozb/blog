# blog

GitHub Pages と Jekyll で公開しているブログです。

- 公開先: <https://opoblblfozb.github.io/blog/>
- `main` ブランチに push すると、GitHub 側でビルドされて数分で反映されます。

## 記事を追加する

1. `_posts/` に `YYYY-MM-DD-<英数字のスラッグ>.md` という名前でファイルを作ります。
2. ファイルの先頭に次の front matter を書き、その下に本文を Markdown で書きます。

   ```yaml
   ---
   layout: post
   title: 記事のタイトル
   date: 2026-11-24
   ---
   ```

3. 画像は `assets/images/` に置き、本文からは次のように参照します。

   ```liquid
   ![説明]({{ '/assets/images/<ファイル名>' | relative_url }})
   ```

4. commit して `main` に push します。

## 構成

| パス | 役割 |
| --- | --- |
| `_config.yml` | サイト名・URL・テーマなどの設定 |
| `index.md` | 記事の一覧を表示するトップページ |
| `_posts/` | 記事 |
| `assets/images/` | 記事で使う画像 |
| `Gemfile` | ローカルでプレビューするときの依存関係 |

## ローカルでプレビューする

Ruby 3.0 以上が必要です。macOS 標準の Ruby 2.6 では `bundle install` が失敗します。

```sh
bundle install
bundle exec jekyll serve
```

起動したら <http://localhost:4000/blog/> を開きます。
