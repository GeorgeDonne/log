---
header:
    teaser: "/assets/images/mm-teaser-cool-stuff.jpeg"

tags:
  - cool stuff
  - testing

toc: true
toc_label: "目录"
#toc_icon: "far fa-cog"
toc_icon: "fas fa-folder-plus"
toc_sticky: true

gallery:
  - url: /assets/images/unsplash-image-1.jpg
    image_path: /assets/images/unsplash-image-1.jpg
    alt: "placeholder image 1"
    title: "Image 1 title caption"
  - url: /assets/images/unsplash-image-2.jpg
    image_path: /assets/images/unsplash-image-2.jpg
    alt: "placeholder image 2"
    title: "Image 2 title caption"
  - url: /assets/images/unsplash-image-3.jpg
    image_path: /assets/images/unsplash-image-4.jpg
    alt: "placeholder image 3"
    title: "Image 3 title caption"

feature_row:
  - image_path: /assets/images/unsplash-image-2.jpg
    alt: "placeholder image 1"
    title: "Placeholder 1"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
  - image_path: /assets/images/unsplash-image-6.jpg
    alt: "placeholder image 2"
    title: "Placeholder 2"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--inverse"
  - image_path: /assets/images/unsplash-image-11.jpg
    title: "Placeholder 3"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."

---

# cs--feature-row

{% include feature_row %}

# cs--figure

{% include figure image_path="/assets/images/unsplash-image-10.jpg" alt="this is a placeholder image" caption="This is a figure caption." %}


# cs--fontawesome


icon: "fab fa-fw fa-twitter-square"
- fab fa-twitter-square 是图标的名字。详见[链接](https://fontawesome.com/v5/icons/twitter-square?f=brands&s=solid)
- fa-fw 是指固定宽度。更多信息科参考[链接](https://fontawesome.com.cn/v4/examples)

# cs--gallery

{% include gallery caption="This is a sample gallery with **Markdown support**." %}

# cs--image alignment

![image-center](/assets/images/unsplash-image-6.jpg){: .align-center}
![image-full](/assets/images/unsplash-image-6.jpg){: .full}
![image-center](/assets/images/logo-apple-touch-icon.png){: .align-center}
![image-full](/assets/images/logo-apple-touch-icon.png){: .full}
assets/images/logo-apple-touch-icon.png
# cs--notice

**ProTip:** Be sure to remove `/docs` and `/test` if you forked Minimal Mistakes. These folders contain documentation and test pages for the theme and you probably don’t want them littering up your repo.
{:.notice--info}
hint: text above is in 'notice--info' style.

Note: The theme uses the jekyll-include-cache plugin which will need to be installed in your Gemfile and added to the plugins array of _config.yml. Otherwise you’ll throw Unknown tag 'include_cached' errors at build.
{:.notice--warning}

