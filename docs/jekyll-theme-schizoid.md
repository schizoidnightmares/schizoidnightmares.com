---
title: jekyll-theme-schizoid
description: The theme I use for my Jekyll-built websites.
---

This is the gem-based theme I use for my <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>-built websites.

- <a href="https://rubygems.org/gems/jekyll-theme-schizoid" target="_blank">view on RubyGems
- <a href="https://github.com/schizoidnightmares/jekyll-theme-schizoid" target="_blank">view on GitHub</a>
{: .arrow}

Also consider viewing <a href="https://github.com/schizoidnightmares/schizoidnightmares.com" target="_blank">this website's GitHub repository</a> or <a href="https://github.com/schizoidnightmares/absurdrealms.com" target="_blank">this one</a> to see how I set it up using this theme.

{% include toc.html %}

## Licence
- <a href="https://github.com/schizoidnightmares/jekyll-theme-schizoid/blob/master/LICENSE" target="_blank">MIT License</a>

## Dependencies
- <a href="https://www.ruby-lang.org/en/" target="_blank">Ruby</a> >= 2.5.0

The gem should automatically install the following for you if not already:
- <a href="https://rubygems.org/gems/jekyll" target="_blank">jekyll</a> ~> 4.3.1
- <a href="https://rubygems.org/gems/jekyll-feed" target="_blank">jekyll-feed</a> ~> 0.12
- <a href="https://rubygems.org/gems/jekyll-paginate-v2" target="_blank">jekyll-paginate-v2</a> ~> 3.0.0
- <a href="https://rubygems.org/gems/jekyll-sitemap" target="_blank">jekyll-sitemap</a> ~> 1.4.0
- <a href="https://rubygems.org/gems/jekyll-tidy" target="_blank">jekyll-tidy</a> ~> 0.2.2
- <a href="https://rubygems.org/gems/jekyll-last-modified-at" target="_blank">jekyll-last-modified-at</a> ~> 1.3.0

## Install
You may want to consider reading Jekyll's <a href="https://jekyllrb.com/docs/themes/" target="_blank">official doc on installing themes</a>.

### RubyGems
1. Add ```gem "jekyll-theme-schizoid", "~> 2.0.0"``` to your site's Gemfile.
1. Run the command ```bundle install``` in your site's directory.
1. Add ```theme: jekyll-theme-schizoid``` to your site's _config.yaml.

## Features
- responsive design
- for use with dark themes based off <a href="https://m3.material.io/" target="_blank">Material Design 3</a>
    - see <a href="https://www.figma.com/community/plugin/1034969338659738588/Material-Theme-Builder" target="_blank">their builder on Figma</a>
- no JavaScript, cookies, or trackers
- basic header and footer menus
- story pages (with bottom navigation)
- landing pages
- supports up to five headings (dynamic spacing)
- different list types, colour boxes, individual page styles, basic SEO, table classes, functional classes, and various front matter options

### Layouts and their uses
blog
: for blog pages (displays posts)

default
: useful base HTML structure

error
: for error pages (e.g. 404)

home
: for the home landing page

landing
: for other landing pages

page
: for normal pages

post
: for blog posts

story
: for story scenes

## Main settings
The recommended settings for your site's _config.yaml:

```
# jekyll-theme-schizoid config
theme-schizoid:
  hideFooter: false
  hideFooterCredit: false

# default front matter
defaults:
  -
    values:
      style: style.css
      showSiteTitle: true
      showPageTitle: true
      display_last_modified_at: true
  -
    scope:
      type: pages
    values:
      layout: page
  -
    scope:
      type: posts
    values:
      layout: post
      category: news

# extras      
kramdown:
  parse_block_html: true
  footnote_backlink: ↑
sass:
  style: compressed
  sourcemap: never
pagination:
  enabled: true
  per_page: 7
  permalink: /:num/
  title: :title
  sort_reverse: true
feed:
  excerpt_only: true
  posts_limit: 7
```

### theme-schizoid
hideFooter
: true — hides the footer
: false — shows the footer

hideFooterCredit
: true — hides the theme's credit in the footer
: false — shows the theme's credit in the footer

## Override theme colours
The theme uses the following defaults you can override in your own /assets/css/style.scss file. Insert the following (replace the colour values as needed, remove the ones you don't wish to change):

```
---
---
// override theme defaults

// colour theme
// numbers in the comments below refer to their colour value in Material Design 3
$color-highlight: #dde3ea; // 90
$color-highlight-bg: #72787e; // 50
$color-link: #ecf1f9; // 95
$color-primary: #c1c7ce; // 80
$color-secondary: #a6acb3; // 70
$color-tertiary: #8b9198; // 60
$color-border: #595f65; // 40
$color-shade: #2b3137t; // 20
$color-bg: #161c21; // 10

@import "{% raw %}{{ site.theme }}{% endraw %}";
```

## Front matter
A layout can use the same front matter as the layout it inherits.

<div class="table">

| layout | inherits
| - | -
| blog | default
| default |
| error | landing
| home | default
| landing | default
| page | default
| post | default
| story | default
{: .compact .small}

</div>

### Layouts
<div class="table">

| variable | usage | default | layouts
| - | - | - | -
| masterClass | *string*<br>the class(es) of the wrapping div of all page content (including header and footer), can leave blank if undesired | ```nil``` | default
| header | *boolean*<br>whether to display the header (top navigation) | ```false``` | default
| contentClass | *string*<br>the class(es) of the wrapping div of all page content (excluding header and footer), can leave blank if undesired | ```nil``` | default
| footer | *boolean*<br>whether to display the footer (bottom navigation) | ```false``` | default
{: .small}

</div>

### Pages
<div class="table">

| variable | usage | default | layouts
| - | - | - | -
| style | *string*<br>the stylesheet to use in /assets/css/<br>e.g. ```style: style.css``` | ```nil```<br>recommend you set the page matter default in _config.yaml | default
| description | *string*<br>page's description for SEO<br>e.g. ```description: Welcome to my website.``` | ```nil``` | default
| showSiteTitle | *boolean*<br>whether to show the site's title (as defined in config_yaml as ```title``` or ```site.title``` as a Liquid variable) in the page's browser tab | ```false``` | default
| showPageTitle | *boolean*<br>whether to show the page's title (as defined in the page's front matter as ```title```) in the page's browser tab <br>recommend you set the page matter default in _config.yaml | ```false``` | default
| display_last_modified_at | *boolean*<br>whether to show in the footer when the page was last modified<br>recommend you set the page matter default in _config.yaml | ```false``` | default
| titleDisplay | *string*<br>an alternative title for the page that displays as the first heading, leave ```nil``` if undesired | ```nil``` | home<br>landing<br>page<br>post<br>story
| img_src | *string*<br>the header image to use after the page's first heading (store images in /assets/images/), resized to 700px in width while retaining original aspect ratio<br>e.g. ```img_src: placeholder.jpg```<br><br>leave ```nil``` if undesired | ```nil``` | page<br>post<br>story
| img_larger | *boolean*<br>open the header image's original size if the user clicks on the image | ```false``` | page<br>post<br>story
| img_alt | *string*<br>the alt text for the header image | ```nil``` | page<br>post<br>story
| img_caption | *string*<br>the caption for the header image | ```nil``` | page<br>post<br>story
| number | *string*<br>the story's scene number (has no effect on navigation)<br>e.g. ```number: Opening``` | ```nil``` | story
| storyNQ | *boolean*<br>whether *not* to display the story's scene title surrounded by quotation marks | ```false``` | story
| storyURL | *string*<br>the URL of the scene's story | ```nil``` | story
| story | *string*<br>the scene's story title | ```nil``` | story
| published | *string*<br>the story's scene publication date (purely cosmetic, does not change anything else) | ```nil``` | story
| scene | *string*<br>the type of scene in the story<br>set as ```opening```, ```ending```, or leave blank | ```nil``` | story
| previous_scene | *string*<br>the URL or destination of the scene that comes before this one, leave blank if opening | ```nil``` | story
| wip | *boolean*<br>whether the scene is part of a story that is a work in progress | ```false``` | story
| next_scene | *string*<br>the URL or destination of the scene that comes after this one, leave blank if opening or story is a WIP | ```nil``` | story
{: .small}

</div>

## Includes
colorbox.html
: displays a coloured box (e.g. {% include colorbox.html color="blue" %})
: use the ```color``` variable to define its colour
: example usage: ```{% raw %}{% include colorbox.html color="blue" %}{% endraw %}```

contact.html
: displays a link to a contact page
: define the following below in _config.yaml

```
contact:
  url: # the URL or destination of the contact page
  target: # the target of the link (e.g. _blank), leave undefined/blank if undesired
```

footer.html
: inserts the footer menu (footer items defined in /_data/footer.yaml)

header.html
: inserts the header menu (header items defined in /_data/header.yaml)

image.html
: inserts image container
: see the following below for variables

<div class="table">

| variable | usage | default
| - | - | -
| class | *string*<br>the class(es) of the ```.figure```, can leave blank<br><br>use ```left``` to float image left, use ```right``` to float right | ```nil```
| width | *string*<br>width in px but specify only numerals, retains aspect ratio, can leave blank | ```nil```
| larger | *boolean*<br>open the image's original size if the user clicks on the image | ```false```
| src | *string*<br>where the image is located in /assets/images/ | ```nil```
| alt | *string*<br>the alt text | ```nil```
| caption | *string*<br>caption displayed below the image in the same container | ```nil```
{: .small}

</div>

toc.html
: inserts table of contents

wip.html
: define ```percent``` or define ```wip``` if percent is in /_data/wip.yaml

## Classes
<div class="table" markdown=0>
  <table class="small">
    <tr><th>class</th><th>usage</th><th>example</th></tr>
    <tr>
      <td>left</td>
      <td>floats content left</td>
      <td>
        <pre class="highlight"><code>&lt;div class="table left" markdown=0&gt;
  &lt;table&gt;
    &lt;tr&gt;&lt;th&gt;test&lt;/th&gt;&lt;/tr&gt;
    &lt;tr&gt;&lt;td&gt;test&lt;/td&gt;&lt;/tr&gt;
  &lt;/table&gt;
&lt;/div&gt;</code></pre>
      </td>
    </tr>
    <tr>
      <td>right</td>
      <td>floats content right</td>
      <td></td>
    </tr>
    <tr>
      <td>nbText</td>
      <td>non-breaking text</td>
      <td>
        <pre class="highlight"><code>Test
{: .nbText}</code></pre>
      </td>
    </tr>
    <tr>
      <td>darkText</td>
      <td>changes text to a dark colour (for use on light backgrounds)</td>
      <td></td>
    </tr>
    <tr>
      <td>nip</td>
      <td>no indent paragraph</td>
      <td></td>
    </tr>
    <tr>
      <td>small</td>
      <td>reduces text size</td>
      <td></td>
    </tr>
  </table>
</div>

### Lists
<div class="table" markdown=0>
  <table class="small">
    <tr><th>class</th><th>usage</th><th>example</th></tr>
    <tr>
      <td>spaced</td>
      <td>adds extra space between items</td>
      <td>
        <pre class="highlight"><code>- Test
- Test
{: .spaced}</code></pre>
      </td>
    </tr>
    <tr>
      <td>lowercase</td>
      <td>changes list type to lowercase alphabet</td>
      <td></td>
    </tr>
    <tr>
      <td>arrow</td>
      <td>arrow list type (for use as buttons)</td>
      <td></td>
    </tr>
    <tr>
      <td>columns2</td>
      <td>splits list into two columns, reduces font size accordingly<br>recommend using this for lists greater than 10 items</td>
      <td></td>
    </tr>
    <tr>
      <td>columns3</td>
      <td>splits list into three columns, reduces font size accordingly<br>recommend using this for lists greater than 20 items</td>
      <td></td>
    </tr>
  </table>
</div>

### Tables
<div class="table" markdown=0>
  <table class="small">
    <tr><th>class</th><th>usage</th><th>example</th></tr>
    <tr>
      <td>table</td>
      <td>for use in all tables on a page, wrap them in a div</td>
      <td>
        <pre class="highlight"><code>&lt;div class="table"&gt;

| test | test
| - | -
| test | test

&lt;/div&gt;</code></pre>
      </td>
    </tr>
    <tr>
      <td>center</td>
      <td>centres text in a table</td>
      <td>
        <pre class="highlight"><code>&lt;div class="table"&gt;

| test | test
| - | -
| test | test
{: .center}

&lt;/div&gt;</code></pre>
      </td>
    </tr>
    <tr>
      <td>small</td>
      <td>reduces font size in a table</td>
      <td></td>
    </tr>
    <tr>
      <td>blc</td>
      <td>removes the borders of table cells</td>
      <td></td>
    </tr>
    <tr>
      <td>borderless</td>
      <td>removes all of a table's borders</td>
      <td></td>
    </tr>
    <tr>
      <td>compact</td>
      <td>sets table width to only the width of its contents rather than full content page width</td>
      <td></td>
    </tr>
    <tr>
      <td>infobox</td>
      <td>for use with infoboxes<br>centres and increases the size of table headers</td>
      <td></td>
    </tr>
  </table>
</div>