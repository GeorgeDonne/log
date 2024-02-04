---
layout : single
# classes: wide
canonical_url: # "https://yoursite.com/custom-canonical-url"
header:
    teaser: /assets/images/mm-teaser-website.png

show_date: true
#last_modified_at: 2023-10-19T16:20:02-05:00
date: 2023-10-30T12:00:00+08:00
#last_modified_at: 2023-10-30T12:14:00-05:00 # unknown to display time, by George on 2023-10-19

tags:
  - minimal-mistakes theme
  - jekyll
categories:
  - gd-log
  - build websites

share: false

author_profile: false

toc: true
toc_label: "目录"
#toc_icon: "far fa-cog"
toc_icon: "fas fa-folder-plus"
toc_sticky: true

header:
  image: /assets/images/unsplash-image-1.jpg
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"

excerpt: "This post should display a **header with an overlay image**, if the theme supports it."
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"
    - label: "Foo Button"
      url: "#foo"
    - label: "Bar Button"
      url: "#bar"
---

# 复制mm theme

```zsh
~ % git clone git@github.com:GeorgeDonne/log.git gwlog
Cloning into 'gwlog'...
remote: Enumerating objects: 16950, done.
remote: Total 16950 (delta 0), reused 0 (delta 0), pack-reused 16950
Receiving objects: 100% (16950/16950), 44.33 MiB | 2.79 MiB/s, done.
Resolving deltas: 100% (10116/10116), done.
Updating files: 100% (743/743), done.
```

```zsh
~ % cd gwlog
~/gwlog % git branch -av
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)
```

**在本地创建 dev 分支**

查看所有分支
~/gwlog % git branch -av
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)

查看本地分支和远程分支的对应关系
~/gwlog % git branch -vv
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

创建本地分支dev
查看所有分支。有了本地分支dev
查看本地和远程分支的对应关系。发现dev没有和远程分支对应起来
~/gwlog % git branch dev
~/gwlog % git branch -av
  dev                   8a67ce8e Improve PR close auto-comment message (#3713)
* master                8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/HEAD   -> origin/master
  remotes/origin/dev    8a67ce8e Improve PR close auto-comment message (#3713)
  remotes/origin/master 8a67ce8e Improve PR close auto-comment message (#3713)
~/gwlog % git branch -vv
  dev    8a67ce8e Improve PR close auto-comment message (#3713)
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

将本地分支dev和远程分支关联起来
查看对应关系。已对应起来了。
~/gwlog % git branch --set-upstream-to=origin/dev dev
branch 'dev' set up to track 'origin/dev'.
~/gwlog % git branch -vv
  dev    8a67ce8e [origin/dev] Improve PR close auto-comment message (#3713)
* master 8a67ce8e [origin/master] Improve PR close auto-comment message (#3713)

参考资料：
在Git中创建本地分支并关联远程分支；https://blog.csdn.net/yanwennian/article/details/133860421

切换到dev分支，开始工作……
~/gwlog % git switch dev
Switched to branch 'dev'
Your branch is up to date with 'origin/dev'.

# 修改mm theme

通读2遍文档https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/，摘录下能读懂的部分，以及感兴趣的部分。
Personal Website with Minimal Mistakes Jekyll Theme HOWTO - Part II。（[链接](https://www.cross-validated.com/Personal-website-with-Minimal-Mistakes-Jekyll-Theme-HOWTO-Part-II/)）

- mm-theme 的 Configuration。([链接](https://mmistakes.github.io/minimal-mistakes/docs/configuration/))
- mm-theme 的 Layout。([链接](https://mmistakes.github.io/minimal-mistakes/docs/layouts/))
- mm-theme 的 Utility Classes。([链接](https://mmistakes.github.io/minimal-mistakes/docs/utility-classes/))
- mm-theme 的 Helper。([链接](https://mmistakes.github.io/minimal-mistakes/docs/helpers/))


## 删除文件

删除以下文件。
参考信息：https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/

- .editorconfig
- .gitattributes
- .github
- /docs
- /test
- CHANGELOG.md
- 不能删除，否则jekyll build报错 // minimal-mistakes-jekyll.gemspec
- README.md
- screenshot-layouts.png
- screenshot.png

## 网站设置/Site Setting

- 皮肤/skin/颜色主题/color scheme。
  - 采用了 mm-theme 提供的 default，看上去比较舒服。其他 skin 有点不适合我。
  - 对应配置是 `_config.yml > minimal_mistakes_skin : "default"`
- site.locale/区域。
  - 设置为zh-CN，网站就成为中文版网站了。
  - locale 支持哪些取值，可以直接查看 `_data > ui-text.yml`。
  - 对应配置是 `_config.yml > locale : "zh-CN"`
- 网站标题和副标题/site.title, site.subtitle。
  - title = 乔治PM爱编程
  - subtitle = 制造一些他人喜欢的东西，需要产品经理懂得造什么，以及程序员用什么技术造出来。
- site.name/网站的作者名
  - 设置为 George Donne （这是我的英文名字）
  - 对应配置是 `_config.yml > name : "George Donne"`
  - 用途尚不明确
- site.description/对作者的简要描述
  - 设置为 A Product Manager Loving Coding
  - 对应配置是 `_config.yml > description : "A Product Manager Loving Coding"`
  - 用途尚不明确
- site.description/对作者的简要描述
  - 设置为 A Product Manager Loving Coding
  - 对应配置是 `_config.yml > description : "A Product Manager Loving Coding"`
  - 用途尚不明确
- site.teaser/每篇博客底部的猜你喜欢用的图片
  - 跳过
  - 设置到了每一篇博客的顶部，才有意义 (This image can be overridden at anytime by applying the following to a document’s YAML Front Matter.)。
  ```yaml
  比如在博客"2023-10-17-build-personal-website.md"的顶部YAML设置
  ---
  header:
      teaser: /assets/images/mm-teaser-website.png
  ---
  ```
- site.logo/网站的logo
  - 对应配置是 `_config.yml > logo : "/assets/images/logo-apple-touch-icon.png"`
- site.masthead_title
  - 会覆盖掉上述的site.title
  - 跳过不设置  
- site.breadcrumbs/面包屑
  - 还是有用处的。设置为true。
  - 对应配置是 `_config.yml >  breadcrumbs : true`
- show_date/博客是否显示日期
  - 在每个博客的 Front Matter YAML中设置 `show_date: true` 或 `show_date: false` 予以显示或不显示博客的发表日期。
  - 可以在_config.yml中设置default值，则可以省却在每个博客中设置。
  - 当前在_config.yml中设置default值为 `show_date: true`。
- site.date_format/面包屑
  - 应该是网站的全局设置，无法在某个博客单独设置
  - 对应配置是 `_config.yml >  date_format: "%Y-%m-%d %H:%M:%S"`
  - 更多信息可参考[cheatsheet](https://www.shortcutfoo.com/app/dojos/ruby-date-format-strftime/cheatsheet)
- site.auto_feed
  - 先关闭了，对应配置是 `_config.yml > atom_feed: > hide: true`
  - 如何隐藏“关注”2字？

- site.search/搜索
  - 设置为打开。
  - 对应配置是 `_config.yml > search: true` 和 `_config.yml > search_full_content: true`
- 社交媒体分享
  - 每个博客可以关闭分享，可以在每个博客顶部YAML设置 `share: false`
  - 也可以在 _config.yml 设置 default 值。
- 设置网站 author 信息
  - 电子邮箱/email 可有2种设置方式，`_config.yml > author > email` 或 `_config.yml > author > links > url :"mailto:GeorgeDonneV2@outlook.com"`，采用了后一种方式，更灵活（比如可以修改图标）。
  - 其他相关社交媒体链接，先关闭。
  
- 设置网站底部的关注
  - 通过设置 `_config.yml > footer: > links:`的 `label` `icon` `url` 实现。
  - 设置了 github。其他后续再增加。
- 首页的分页显示数量
  - 首页的分页显示数量，通过设置 `_config.yml > paginate: 10` 实现。
  - 其他页的分页显示数量，待研究如何设置。

- 增加按年份归档
  - 在 `_data > navigation.yml > main:` 下增加 title 和 url：
  
    ```yaml
    - title : "归档" 
      url   : /posts-by-year/ # /year-archive/
    ```
  
  - 增加文件 `_pages > year_archive.md`，内容如下：
  
    ```yaml
    ---
    title: "按年份" #"Posts by Year"
    permalink: /posts-by-year/ # 和 navigation.yml 中的 url 对应起来
    layout: posts # 不要改成其他 layout，否则显示不出来
    author_profile: true
    ---
    ```
  - 运行 bundle exec jekyll build 重新构建。使用 jekyll build 重新构建则不能得到预期效果。

- 增加按标签tags归档
  - 增加文件 `_pages > gd-tag-archive.md`，内容如下：
  
    ```yaml
    ---
    title: "按标签" # "Posts by Tags"
    permalink: /posts-by-tags/ # /tags/
    layout: tags # 必须是 tags
    author_profile: true
    entries_layout: grid # grid视图
    classes: wide
    ---
    按[年份](/posts-by-year/)
    ```
  - 运行 bundle exec jekyll build 重新构建。使用 jekyll build 重新构建则不能得到预期效果。

- 增加按类别categories归档
  - 增加文件 `_pages > gd-cats-archive.md`，内容如下：
  
    ```yaml
    ---
    title: "按类别"
    permalink: /posts-by-cats/ 
    layout: categories # 必须是 categories
    author_profile: true
    ---
    按[年份](/posts-by-year/)，按[标签](/posts-by-tags/)
    ```
  - 运行 bundle exec jekyll build 重新构建。使用 jekyll build 重新构建则不能得到预期效果。
  
- 修改 path 确保点击面包屑正确
  ```yaml
  category_archive:
    type: liquid
    path: /posts-by-cats/ # 和 _pages > gd-cats-archive.md > permalink 保持一致
  ```
- 对于每个博客的布局/layout
  - `layout: single` 是比较合适的
  - `layout: single` + `classes: wide` 也是不错的。 
  - `layout: splash` 不大合适。  

- 页面顶部显示大幅图片
  - 在Front Matter 增加 `header > image : /assets/images/photo.png` 即可实现。
  - 适用于：根目录的 index.html，_posts 目录下各个博客。
  - 比如在根目录 index.html 的Front Matter增加如下：
    ```yaml
    ---
    header:
    image: /assets/images/unsplash-image-1.jpg
    caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
    ---
    ```

- 在社交媒体分享博客
  - 在某个博客布局是 `layout: single`，则可在该博客的Front Matter 设置 `share: true`，打开社交媒体分享。
  - 分享哪些社交媒体，可以更改 `_includes/social-share.html`。

- 修改正文字体大小
  - 修改 `_sass/minimal-mistakes/_page.scss`
  - 找到 `.page__content`，修改 p li dl 的 font-size。比如从 1em 改为 0.9em。
    ```css
    .page__content {
      p,
      li,
      dl {
        font-size: 0.9em; /* update from 1em to 0.9em, by George on 2023-10-19*/
      }
    }
    ```
- 修改宽度
My MacBook Pro has dimensions larger than $max-width specified in _page.scss like so:

@include breakpoint($x-large) {
    max-width: $max-width;
  }
$max-width currently is 1280px and lives in _variables.scss. I have increased it to 1400px to have more space for content.

- 修改链接颜色
$link-color: #007bb6 !default; /* add by George on 2023-10-21 */

- //修改toc位置
https://github.com/mmistakes/minimal-mistakes/issues/1298

- 修改宽度
  - Ability to disable left sidebar in single layout #1322，https://github.com/mmistakes/minimal-mistakes/issues/1322
  - 修改navigation.scss 中的面包屑，类似修改width 100%

# 信息

**Note:** for technical reasons, `_config.yml` is NOT reloaded automatically when used with `jekyll serve`. If you make any changes to this file, please restart the server process for them to be applied.
{:.notice--warning}

## Jekyll Front Matter Defaults 设置

参考[链接](https://jekyllrb.com/docs/configuration/front-matter-defaults/)

```yaml
defaults: # 可以有多个scope/values对
  -
    scope: # 通过 path + type 确定scope
      path: "" # 空表示适用于所有文件
      type: "pages" # 取值：pages, posts, drafts, collection名字(自定义的)
    values:
      layout: "my-site"
  -
    scope:
      path: "projects"
      type: "pages" # previously `page` in Jekyll 2.2.
    values:
      layout: "project" # overrides previous default layout
      author: "Mr. Hyde"
```
## 构建刷新

修改了一些 url 的设置后，用 jekyll build 重新构建，发现在 _site 下没有生成期望的目录。
此时，可以执行 bundle exec jekyll build，就可以看到 _site 下生成期望的目录了。

## 有用的总结

https://www.fabriziomusacchio.com/blog/2021-08-11-Minimal_Mistakes_Cheat_Sheet/
https://www.fabriziomusacchio.com/blog/2021-08-12-Liquid_Cheat_Sheet/

# 一些有用的tips

- 用{:.notice}编写一些摘要等。即醒目又方便。

# TTD

- 2023-10-17 -- 待学习 kramdown
- 2023-10-18 -- 待设置 site.comment
- 2023-10-19 -- 待学习 Jekyll 的 collection
- 2023-10-19 -- 待学习“如何在md中引用图标”
- 2023-10-26 -- author_profile: false 不写时，顶部出现一些不期望的文字，可能是sidebar没有处理好。

- 关闭//2023-10-17 -- 待学习 Jekyll 的 default 如何设置
