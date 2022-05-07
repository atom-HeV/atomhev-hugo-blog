---
title: タイトルとURL問題の解決
slug: wowchemy-slug-solution
date: 2022-05-06T20:37:39.678Z
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
[前の記事](/post/wowchemy-slug-issue/)の問題が解決した



WowchemyはNetlifyのCMSを用いて編集でき、その編集可能な項目にSlugがないのが問題だった。
CMSで編集可能な項目はstatic/admin/config.ymlによって変更できるが、Wowchemyではモジュールとしてその設定が用意されているため、そのままでは利用者側から変更できない。そこで、そのモジュールの使用をやめ、自分でCMSの設定を行うことにした。

Wowchemyの公式ドキュメントではconfig/_default/config.yamlでモジュールをdisable: trueにすると、モジュールCMSの設定を無効化できるとされているが、それではうまくいかなかった。


実際に行った手順を示す。

1.content/_default/config.yamlのparmalinksをpost: '/post/:slug'の用に設定
2.content/adminフォルダを削除。
3.static/adminフォルダを作成
4.static/adminに公式ドキュメントの[Getting Started With Netlify CMS](https://www.netlifycms.org/docs/hugo/#getting-started-with-netlify-cms)にあるindex.htmlを配置。
5.static/adminに[github上のwowchemy-cmsのconfigファイル](https://github.com/wowchemy/wowchemy-hugo-themes/blob/main/wowchemy-cms/data/wowchemy_cms_tpl.yaml)をconfig.ymlとして配置。（注意：.yamlではなく.yml）
6.static/admin/config.ymlのcollection: -name: postsにslug: '{{fields.slug}}'を追記。collection: -name: posts: fields:に- {label: "URL", name: "slug", widget: "string"}を追記。

これらをデプロイすると、CMS上のでSlugが編集可能になる。URLという名前の項目にURLにしたい文字列を入力する。



解決に時間がかかってしまったため、途中の作業に自信がない。解決しなかった場合は私のTwitterのDMまで。