# Memoir is a premium Jekyll theme for writers and photographers

Memoir was developed by [Ivan Chromjak](https://ivanchromjak.com) for [jekyll.plus](https://jekyll.plus/), theme [live demo](https://memoir.jekyll.plus/) available.

![Memoir template screenshot](/assets/img/screenshot.jpg)

## Features

* Contact form
* Responsive videos
* Image lightbox
* Image slideshow
* Google maps
* Contact form (FormSpree)
* Pre-built pages
* Blog with pagination
* Post category page
* Disqus comments for posts
* Light and dark themes
* Configurable header and footer with images
* Optimised for [GitHub](https://pages.github.com/) pages
* RSS feed
* SEO tags
* Google Analytics


## Installation

Install the dependencies with [Bundler](http://bundler.io/):

```bash
bundle install
```

Run the following to generate your site:
```bash
bundle exec jekyll serve
```

You can find more on [Deployment Methods](https://jekyllrb.com/docs/deployment-methods/) page on Jekyll website.

## Setup

### Site and author details
Add your site and author details in `_config.yml`:
```yaml
# Site title and description
title:              Momoir - Jekyll Template for Story Tellers
description:        Hi, I'm Memoir, an awesome Jekyll bloging theme.

# Permalink URLs structure, for permalink style options see: https://jekyllrb.com/docs/permalinks/
permalink:          /:title/

# Site logo, image or text
logo:               # e.g. logo.png, upload logo image file to /assets/img/ folder
logo_text:          Memoir      # if the above "logo:" image variable  is not set, this text logo is displayed instead

# Author settings, displayed on about page
author:
    name:           John Smith
    bio:            Hi, I'm John, a web designer, father, human and the author of this blog.
    email:          john@somewebsite.com
    website:        http://somewebsite.com
    facebook:       https://www.facebook.com/
    flickr:         https://flickr.com/
    dribbble:       https://dribbble.com/
    github:         https://github.com/
    googleplus:     https://plus.google.com/
    instagram:      https://www.instagram.com/
    linkedin:       https://www.linkedin.com/feed/
    pinterest:      https://www.pinterest.com/
    twitter:        https://twitter.com/
    vimeo:          https://vimeo.com/
    youtube:        https://www.youtube.com/

# Social share buttons
twitter_username:   ivanchromjak
github_username:    ivanchromjak
```

### Navigation Bar
Set in the main navigation links in `_data/navigation_header.yml`:
```yaml
- title: About
  url: /about/
```

### Footer

Edit copyright notice in `_config.yml`:
```yaml
footer:
    copyright:
```

Set in the navigation links in `_data/navigation_footer.yml`:
```yaml
- title: About
  url: /about/
```

### Enabling comments (via Disqus)

Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each post. To enable it, add the following lines to your Jekyll site:

```yaml
disqus:
    shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`. If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.

### Google Analytics

To enable Google Anaytics, add the following lines to your Jekyll site:

```yaml
  google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

### Google Map

To display Google map on contact page, add the following in your page content, replacing latitude, longitude and zoom values:

```yaml
{% include map.html latitude="40.6700" longitude="-73.9400" zoom="16" %}
```

### Contact Form (via FormSpree)

Submit the form and confirm your email address at [FormSpree](https://formspree.io/). Then add the following lines to contact page YAML Front Matter, replacing the email address:

```yaml
formspree:
    email: my_name@gmail.com
    redirect: /thanks/
```

### Update favicon

You can find the current favicon (favicon.png) inside the theme `/assets/img/` directory, just replace it with your new favicon.

## Posts

To create a new post, you can create a new markdown file inside the `_posts` directory by following the recommended file naming format:
```
YEAR-MONTH-DAY-title.MARKUP
```
Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

Post requires front matter, everything in between the first and second --- are part of the YAML Front Matter, and everything after the second --- will be rendered with Markdown and show up as “Content”.
The following is a post file with different configurations you can add as example:

```yaml
---
layout: post
title: How To Travel On Low Budget
subtitle: China and Nepal
categories: [Travel, Photography]
header:
    image: ocean.jpg    # local image e.g oceam.jpg or remote e.g https://source.unsplash.com/ZeXP6p7agjE
    align: top          # e.g. top, center or bottom
    text: dark          # e.g. dark or light
---
```

You can rebuild the site in many different ways, but the most common way is to run `bundle exec jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To keep things more organized, add post images to `/assets/posts/` directory, and add theme images to `/assets/img/` directory.

### Adding images
To add an image to a post or page use the following codes:
Local image from `/assets/posts/` directory:
```yaml
{% include image.html img="girl.jpg" alt="Alt for image" caption="Girl on a rock" %}
```
External wide image with lightbox:
```yaml
{% include image.html img="https://source.unsplash.com/TT-ROxWj9nA.jpg" style="wide" lightbox="true" alt="Alt for image" caption="Wide image in lightbox" %}
```

### Adding slideshow
To add a slideshow to a page or post, create a slideshow directory in `/assets/posts/` directory e.g. `/assets/posts/slideshow-1/` and add all slideshow images inside. Then add the following code to page or post:
```yaml
{% include slideshow.html gallery="slideshow-1" %}
```

### Responsive Videos
Embed local videos:
```html
<video controls playsinline uk-video="automute: true">
    <source src="http://www.quirksmode.org/html5/videos/big_buck_bunny.mp4" type="video/mp4">
    <source src="http://www.quirksmode.org/html5/videos/big_buck_bunny.ogv" type="video/ogg">
</video>
```
Embed YouTube videos:
```html
<iframe src="http://www.youtube.com/embed/YE7VzlLtp-4?autoplay=0&amp;showinfo=0&amp;rel=0&amp;modestbranding=1&amp;playsinline=1" width="600" height="340" frameborder="0" allowfullscreen uk-responsive uk-video="automute: true"></iframe>
```

To create a draft post, create the post file under the `_drafts` directory, and you can find more information in [Working with Drafts](https://jekyllrb.com/docs/drafts/).

## Pages

To create a new page, just create a new markdown file inside the root directory. The following is a YAML Front Matter example for a page:

```yaml
---
layout: contact
title: Contact
subtitle: Get in touch
permalink: /contact/
header:
    image: ocean.jpg    # local image e.g ocean.jpg from /assets/posts/ folder or remote e.g https://source.unsplash.com/ZeXP6p7agjE
    align: top          # header image alignment e.g. top, center or bottom
    text: dark          # text color e.g. dark or light
---
```

## Customization

To modify the primary color, open `/assets/css/main.scss` and replace the `#d40c3c` color value:
```scss
// Primary template color
$global-primary-background: #d40c3c;
```

Further style customisation can be done in the following files:
```
/_sass/theme/mixins.scss
/_sass/theme/variables.scss
/assets/css/main.scss
```

## Development

Install [UIkit](https://getuikit.com/) font end framework dependency via Npm:
```bash
npm install
```
Enable live browser reload with the following:
```bash
bundle exec jekyll s --livereload
```

## Credits and Sources

- Google fonts https://fonts.google.com/
- Google analytics https://www.google.com/analytics/
- Google maps https://www.google.com/maps
- UIkit front end framework https://getuikit.com/
- Unsplash images https://unsplash.com/
- Jekyll CML https://jekyllrb.com/

## Support
Customer support is provided through our Envato profile page [contact form](https://themeforest.net/user/pressapps) for up to six months from the purchase date and is provided Monday to Friday during the business week. We aim to answer all support requests daily, most are handled within 48h.
