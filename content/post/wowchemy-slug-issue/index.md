---
title: WowchemyでNetlifyのCMSを用いたときに、タイトルとURLを別で設定したい（ひとまず解決）
slug: wowchemy-slug-issue
date: 2022-05-06T19:32:56.627Z
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
タイトルの通り

CMSで設定したタイトルがそのままURLになってしまうため、タイトルに日本語のようなマルチバイト文字を使っていると、Twitterなどでリンクが機能しなくなってしまう。

slugを設定すれば良いのだが、そのためには直接ファイルに触れる必要があるためCMSの良さが失われる。

現在は直接ファイルを編集している。

[追記：解決しました]({{<relref "/posts/wowchemy-slug-solution/index.md">}})