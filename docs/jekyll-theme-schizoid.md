---
title: jekyll-theme-schizoid
description: The theme I use for my Jekyll-built websites.
---

This is the gem-based theme I use for my <a href="https://jekyllrb.com/" target="_blank">Jekyll</a>-built websites.

- <a href="https://rubygems.org/gems/jekyll-theme-schizoid" target="_blank">view on RubyGems
- <a href="https://github.com/schizoidnightmares/jekyll-theme-schizoid" target="_blank">view on GitHub</a>
{: .arrow}

Also consider viewing <a href="https://github.com/schizoidnightmares/schizoidnightmares.com" target="_blank">this website's GitHub repository</a> to see how I set it up using this theme.

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
- <a href="https://rubygems.org/gems/jekyll-sass-converter" target="_blank">jekyll-sass-converter</a> ~> 3.0.0
- <a href="https://rubygems.org/gems/jekyll-tidy" target="_blank">jekyll-tidy</a> ~> 0.2.2
- <a href="https://rubygems.org/gems/jekyll-last-modified-at" target="_blank">jekyll-last-modified-at</a> ~> 1.3.0

## Install
You may want to consider reading Jekyll's <a href="https://jekyllrb.com/docs/themes/" target="_blank">official doc on installing themes</a>.

### RubyGems
1. Add ```gem "jekyll-theme-schizoid", "~> 1.0.0"``` to your site's Gemfile.
1. Run the command ```bundle update``` in your site's directory.
1. Add ```theme: jekyll-theme-schizoid``` to your site's _config.yaml.

## Features
- responsive design
- for use with dark themes based off <a href="https://m3.material.io/" target="_blank">Material Design 3</a>
    - see <a href="https://www.figma.com/community/plugin/1034969338659738588/Material-Theme-Builder" target="_blank">their builder on Figma</a>
- no JavaScript, cookies, or trackers
- basic header and footer menus
- supports up to four headings (dynamic spacing)
- different list types, colour boxes, individual page styles, basic SEO, table classes, and various front matter options

## Settings
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

### Override theme colours
The theme uses the following defaults you can override in your own /assets/css/style.scss file. Insert the following (replace the colour values as needed, remove the ones you don't wish to change):

```
---
---
@import "{% raw %}{{ site.theme }}{% endraw %}"

/* Neutral-Variant */
$NV100: #ffffff;
$NV99: #fdfbff;
$NV95: #eff0fa;
$NV90: #e0e2ec;
$NV80: #c4c6d0;
$NV70: #a9abb4;
$NV60: #8e9099;
$NV50: #74777f;
$NV40: #5b5e66;
$NV30: #44474e;
$NV20: #2d3038;
$NV10: #181c22;
$NV0: #000000;
```

### Page front matter
style *(all)*
: the stylesheet the page uses (in /assets/css/)

description *(all)*
: the page description for SEO

showSiteTitle *(all)*
: true — displays the site's title in the browser tab
: false — hides the site's title in the browser tab

showPageTitle *(all)*
: true — displays the page's title in the browser tab
: false — hides the page's title in the browser tab

display_last_modified_at *(blog, page, and post)*
: true — displays the page's last modified date in the footer
: false — hides the page's last modified date in the footer

## Layouts
### blog
This layout is for blog pages.
### error
This layout is for error pages. Example below for 404.md:

```
---
layout: error
title: 404
permalink: 404.html
sitemap: false
---

Page not found
```

### home
This layout is for the home landing page, the title links to the first item specified in header.yaml.

### landing
This layout is for landing pages.

### page
This layout is for pages.

### post
This layout is for posts.

## Data
header.yaml
: contains links that may appear in the header

Example:

```
# insert pages you want to appear in the header below
# e.g.
# - title: Page
#   url: /page-url/ (e.g. /terms/)
#   target: _blank
#
# a page using the home layout links to the first listed title's url

- title: About
  url: /about/

- title: News
  url: /news/

- title: Works
  url: /works/

- title: Docs
  url: /docs/

- title: Contact
  url: https://tally.so/r/mOaDRp
  target: _blank
```

footer.yaml
: contains links that may appear in the footer

Example:

```
# insert pages you want to appear in the footer below
# e.g.
# - title: Page
#   url: /page-url/ (e.g. /terms/)
#   target: _blank

- title: Profiles
  url: /profiles/

- title: Terms
  url: /terms/

- title: Disclaimers
  url: /disclaimers/

- title: Licensing
  url: /licensing/

- title: Credits
  url: /credits/
```

## Includes
colorbox.html
: color — the colour shown (default: white)
: e.g. {% raw %}```{% include colorbox.html color="blue" %}```{% endraw %}
: produces {% include colorbox.html color="blue" %}

toc.html
: check the top of this page to see how it appears

## Classes
### Lists
arrow
: make links stand out, good for buttons

```
- Example
{: .arrow}
```

- Example
{: .arrow}

spaced
: extra-spaced list

```
- Example
- Example
- Example
{: .spaced}
```

- Example
- Example
- Example
{: .spaced}

### Tables
tableOverflow
: wrap tables in a div with this class to add scrollbars
: you must add space between div tags and table

```
<div class="tableOverflow">

| 1 | 2 | 3 | 4 | 5 | 6
| - | - | - | - | - | -
| Example table | Example table | Example table | Example table | Example table | Example table

</div>
```

<div class="tableOverflow">

| Example | Example | Example | Example | Example | Example | Example | Example
| - | - | - | - | - | - | - | -
| Example  | Example | Example | Example | Example | Example | Example | Example

</div>

floatLeft
: floats a table to the left

center
: centres a table

small
: shrinks a table's text

borderless
: removes borders from a table

```
| Example | Example | Example
| - | - | -
| Example | Example | Example
{: .borderless}
```

| Example | Example | Example
| - | - | -
| Example | Example | Example
{: .borderless}

compact
: makes a table only as wide as its contents

### Misc
nbText
: makes text non-breaking
: can be used with spans or divs

darkText
: makes text dark (for when on light backgrounds)