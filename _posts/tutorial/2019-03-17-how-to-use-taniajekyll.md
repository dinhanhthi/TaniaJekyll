---
layout: post
title: "How to use TaniaJekyll?"
description: How to set up and use the components & layouts
tags: [how to]
img: usage.svg
categories: tutorial
snippet: 1
math: 1
lang: en
notnumbering: 1
---

In this tutorial, I suppose that you have already [installed TaniaJekyll]({{ site.baseurl }}/how-to-install-taniajekyll), just follow the ones you need and don't forget to leave a comment below.

<div class="alert alert-warning" role="alert">
  I'm not a native English speaker, please ignore my bad expressions!
</div>

Full list of usages can be found [here]({{site.baseurl}}/tutorial/for-the-editors-only). This post only shows **some showcases** of this theme.

{% include toc.html %}

## 5 layouts of posts

You can check on the [index page]({{site.baseurl}}/), there are 5 different layout of posts. If you wanna apply some layout, just indicate fields

- **The source of elements**: `element-source`
- **The type of layout**: using included file **post-layout.html** with keyword `type` to indicate the layout. In this field, you also need to indicate `img-src` (the source of images), `offset` (from which element we show the list of elements) and `limit` (how many elements you wanna show).

For example, below are the codes to show the projects (`type="project"`) I've done in the front page. In this field, I only show the first (`offset=0`) 4 projects (`limit=4`). The list of projects are stores in a data file called **\_data/project.yml** (`site.data.project`). Please open file **index.html** in the repository and then step to section "**project**" to see an example of below descriptions

~~~ {% raw %}
{% assign element-source = site.data.project %}
{% include post-layout.html type="project" img-src="/img/project" source=element-source offset=0 limit=4 %}
{% endraw %} ~~~


### Project

- **Structure**: *Photo - Title - Description*. 
- In this example page, I use this layout as the layout of my projects.

{% include img/full.html src="/img/post/tutorial/project.png" %}

In order to modify this, you can ()

- **Source of elements**: `site.data.project` (*_data/project.yml*). You can also use the sources as a list of posts like other below layouts.
- **Type**: `type="project"`.
- Icons for the projects must be located in **/img/project/**.

~~~ {% raw %}
{% assign element-source = site.data.project %}
{% include post-layout.html type="project" img-src="/img/project" source=element-source offset=0 limit=4 %}
{% endraw %} ~~~

### Reading list

- **Structure**: *Photo - Title - Author - Rating*.
- Specifically used for the list of books.

{% include img/full.html src="/img/post/tutorial/book.png" %}

- Change the number of challenge books in **_data/setting.yml** (`ncb` for the amount and `ncb_year` for the considered year)
- The theme will automatically determine how many book is read in that year.
- Read more on the [front matter setting]({{site.baseurl}}/tutorial/for-the-editors-only#front-matter "For the editors") to see the list of arguments used for this type of post.
- All book covers must be stored in **/img/bookimg/**.

~~~ {% raw %}
{% assign element-source = site.categories.reading %}
{% include post-layout.html type="reading" img-src="/img/bookimg" source=element-source offset=0 limit=4 %}
{% endraw %} ~~~

### Tutorial

- **Structure**: *Icon - Title - Descripton*.
- Used for tutorial posts.

{% include img/full.html src="/img/post/tutorial/tutorial.png" %}

- Check some examples in **_posts/tutorial/**.
- For the free icons, you can use [this site](https://www.flaticon.com/).
- Icons must be located in **/img/turorial/**.

~~~ {% raw %}
{% assign element-source = site.categories.tutorial %}
{% include post-layout.html type="tutorial" source=element-source offset=0 img-src="/img/tutorial" limit=6 %}
{% endraw %} ~~~

### Thought (layout 1)

- **Structure**: *Title - Date*.
- Very simple layout.

{% include img/full.html src="/img/post/tutorial/thought-1.png" %}

~~~ {% raw %}
{% assign element-source = site.categories.thought %}
{% include post-layout.html type="thought" source=element-source offset=0 limit=6 %}
{% endraw %} ~~~

### Thought (layout 2)

- **Structure**: *Photo - Title - Date*.

{% include img/full.html src="/img/post/tutorial/thought-2.png" %}

~~~ {% raw %}
{% assign element-source = site.categories.thought %}
{% include post-layout.html type="thought2" source=element-source offset=0 limit=4 %}
{% endraw %} ~~~

## Front Matter

Begin of each post, you need to be careful to choose the right [front matter](https://jekyllrb.com/docs/frontmatter/) for that post. What's front matter? Something like this

~~~ {%raw%}
---
layout: post
title: How to use TaniaJekyll?
---
{% endraw %} ~~~

There are some already-defined components on TaniaJekyll that you could use (If you don't want to use something, **remember to REMOVE it**). Check more in [this post]({{site.baseurl}}/tutorial/for-the-editors-only#front-matter "For the editors").

## Insert figures

There are a lot of ways you can insert an image in a post. I imitate the idea of photo post in a Medium post so that they are really beautiful with this layout. All of usages can be seen in [this post]({{site.baseurl}}/tutorial/for-the-editors-only#inset-figures). Below are some examples,

A full-width image

{% include img/full.html src="/img/post/thought/palais.jpg" des="A description of the image." %}

Or images can be float to the left or the right of the post,

{% include img/right.html src="/img/post/thought/nghichden.jpg" des="A description of the image." %}

This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it. This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it. This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it. This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it. This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it. This is an example of paragraph to see the effect of the image floating to the side of post. It has no meaning, please not to understand it.

## Side by side figure and content

In the case you wanna create some tutorial posts with a figure on the left and some instructions on the right, you can use this type of shortcode. Please [check this]({{site.baseurl}}/tutorial/for-the-editors-only#side-by-side-figure-and-content) to see how to use it.

<div class="row align-items-center img-aside">
<p class="col-md-6" markdown="1">
![Description]({{site.baseurl}}/img/post/tutorial/locate.jpg)
</p>
<p class="col-md-6" markdown="1">
This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning. This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning. This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning.
</p>
</div>

<div class="row align-items-center img-aside">
<p class="col-md-6 order-md-2" markdown="1">
![Description]({{site.baseurl}}/img/post/tutorial/locate.jpg)
</p>
<p class="col-md-6 order-md-1" markdown="1">
This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning. This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning. This is an example of paragraph to see the effect of side-by-side content and image. Is has no meaning.
</p>
</div>

## Insert boxes

I build this theme based on Boostrap, then you can use all of [its boxes](https://getbootstrap.com/docs/4.1/components/alerts/) in this theme, for example,

<div class="alert alert-primary" role="alert">
  A simple primary alert—check it out!
</div>
<div class="alert alert-secondary" role="alert">
  A simple secondary alert—check it out!
</div>
<div class="alert alert-success" role="alert">
  A simple success alert—check it out!
</div>
<div class="alert alert-danger" role="alert">
  A simple danger alert—check it out!
</div>
<div class="alert alert-warning" role="alert">
  A simple warning alert—check it out!
</div>
<div class="alert alert-info" role="alert">
  A simple info alert—check it out!
</div>
<div class="alert alert-light" role="alert">
  A simple light alert—check it out!
</div>
<div class="alert alert-dark" role="alert">
  A simple dark alert—check it out!
</div>

Please [check this]({{site.baseurl}}/tutorial/for-the-editors-only#insert-boxes) to see how to use it. I also add a **hide/show box**

<div class="tomTat">
<div id="btTomTat" class="collapsed" data-toggle="collapse" href="#ndTomTat">
  <span>Highlights I like</span>
</div>
<div id="ndTomTat" markdown="1" class="collapse multi-collapse ndTomTat">
Contents.
</div>
</div>

and **definition box**

<div class="def-box" markdown="1" id="dn1">
<div class="box-title" markdown="1">
Title
</div>
<div class="box-content" markdown="1">
Content
</div>
</div>

## Steps

You even can add the steps. Please [check this]({{site.baseurl}}/tutorial/for-the-editors-only#steps) to see how to use it.

<div  class="thi-step">

<div class="step">
<div class="step-number"></div>
<div class="step-content" markdown="1">
Content of step 1.
</div>
</div>

<div class="step">
<div class="step-number"></div>
<div class="step-content" markdown="1">
Content of step 2.
</div>
</div>

</div>

## Texts

You can do many things with text like <mark>marked texts</mark> or a keyboard like <kbd>Ctrl</kbd> + <kbd>B</kbd>. You even can make a text be <sbj>more beautiful</sbj> with this. 