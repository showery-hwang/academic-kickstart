---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Hugo ダイレクトり構成"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2019-09-05T16:47:22+09:00
lastmod: 2019-09-05T16:47:22+09:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

``` Hugo new site ＜サイト名＞``` コマンドで作られたダイレクトり構造を簡単に説明します。

### Hugo ダイレクトり構成

- 参考記事：[Directory Structure](https://gohugo.io/getting-started/directory-structure/)

``` Hugo new site ＜サイト名＞``` コマンドを実行すると、下記ダイレクトり構造を含む＜サイト名＞フォルダが作成されます。

```
.
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```

##### archetypes

``` Hugo new ＜パス/ファイル名＞``` コマンドを実行すると、 ``` content ``` フォルダの下に＜パス/ファイル名＞というコンテンツファイルが作成されます。この際、デフォルトで``` archetypes ``` フォルダの下にある ``` default.md ```テンプレートが使われます。なお、コンテンツタイプによって、その他テンプレートも使われます。

例えば、``` hugo new posts/my-first-post.md ``` の場合、下記順番でテンプレートを探し出して利用します。

```
    archetypes/posts.md
    archetypes/default.md
    themes/my-theme/archetypes/posts.md
    themes/my-theme/archetypes/default.md
```

##### config.toml

このファイルは、デフォルトのサイトコンフィグファイルとして使われます。（サイトルート直下の config.toml, config.yaml, config.json ファイル）

詳細について、下記記事を参照できます。
- {Configure Hugo}(https://gohugo.io/getting-started/configuration/#configuration-directory)


##### content

サイトの全てのコンテンツは、このフォルダの下に置きます。
<br/>```content```フォルダ直下のフォルダは、[Content Sections](https://gohugo.io/content-management/sections/)として解釈されます。

例えば、サイトに ```blog```、```articles```と ```tutorials``` の３つセクションがあるとすれば、
<br/>```content/blog```、 ```content/articles```と ```content/tutorials``` という３つのフォルダが必要となります。

##### data

このフォルダの下に、追加データを保持するためのコンフィグファイルを置きます。
<br/>ファイルのフォーマットは、 YAML、JSON、又は TOML のどちらでなければなりません。
- 詳細について　[Data Templates](https://gohugo.io/templates/data-templates/)　を参照できます。

##### layouts

このフォルダの下に、コンテンツのビューを静的なWebサイトにレンダリングする方法を指定する.htmlファイルの形式でテンプレートを保存します。 
<br/>テンプレートには、
- [Lists of Content in Hugo](https://gohugo.io/templates/lists/) 
- [Homepage Template](https://gohugo.io/templates/homepage/) 
- [Taxonomy Templates](https://gohugo.io/templates/taxonomy-templates/) 
- [Partial Templates](https://gohugo.io/templates/partials/) 
- [Single Page Templates](https://gohugo.io/templates/single-page-templates/) 
<br/>などが含まれます。

##### static

このフォルダの下に、画像、CSS、JavaScriptなどのすべての静的コンテンツを保存します。Hugoがサイトを構築すると、静的ディレクトリ内のすべてのアセットがそのままコピーされます。 
<br/>静的フォルダーを使用する良い例は、[verifying site ownership on Google Search Console](https://support.google.com/analytics/answer/1142414?hl=en)。ここでは、Hugoがコンテンツを変更せずに完全なHTMLファイルをコピーするようにします。


