title: Liferay Front-End Development
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---
class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Work in Progress

# {{title}}

christian.berndt@liferay.com

.date[
  Vienna, 20 November 2021
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Customizing Liferay's UI]
1. Frameworks
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Theme Context Contributor
1. Theme Contributor
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Customizing Liferay's UI]

.bottom-bar[
  {{title}}
]

---

# Customizing Liferay's UI

## Overview

* Themes
* Style Books
* Page Layouts
* Web-Content Templates
* Widget Display Templates
* Fragments
* Theme Contributors
* Theme Context Contributors

---

# Themes

## Overview

- Bundle of SCSS-, Freemarker-, Image-, Properties-, and XML-files
- Packaged and deployed as WAR-File (Web Application Archive)
- Configurable for site specific settings (color-schemes, show/hide search, etc.)

---

# Page Layouts

## Overview

* TODO

---

# Web-Content Templates

## Overview

- Format structured Web-Content Articles
- Clean separation of content and presentation
- Implemented with Freemarker templates

---

# Web-Content Templates

## Example: Press Release

.col-6[
### press-release.json
]

.col-6[
### press-release.ftl
]

---

# Web-Content Templates

## Example: Press Release (cont.)

.col-6[
### press-release.xml
]

.col-6[
### Rendered output

* TODO: Add screenshot
]

---

# Widget Display Templates

## Overview

- Lightweight markup customization of Liferay's core applications
- Implemented with Freemarker templates
- Available for set based widgets, e.g. *Asset-Publisher*, *Blogs*, *Breadcrumb*, etc.
- Also available for custom applications

---

# Widget Display Templates

## Example: Asset Publisher

.col-6[

### Cards layout

* TODO: Add screenshot

]

.col-6[

### Carousel

* TODO: Add screenshot

]

---

# Fragments

## Overview

- Aka "Modern Site Building"
- HTML + CSS + Javascript
- Inline editing capabilities
- Meant to be used by "Business Users"

---

# Fragments

## An Example

- TODO: Screenshot, Visually appealing One Pager

---

# Client-Side Javascript Widgets

## Overview

* TODO

---

# Theme Contributors

## Overview

* TODO

---

# Theme Context Contributors

## Overview

* TODO

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. .active[Frameworks]
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Theme Context Contributor
1. Theme Contributor
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Frameworks]

.bottom-bar[
  {{title}}
]

---

# Frameworks

## Overview

* Lexicon
* Clay
* Freemarker

---

# Lexicon

## A design language for the Liferay product ecosystem

* DXP
* Commerce
* Analytics

## Building Blocks

* Foundations (Color, Grid, Typography, Writing Style, and more)
* Components (e.g. Alerts, Buttons, Cards, Dropdown Menu)
* Templates (e.g. Dataset Template, Form Template)

---

# Clay

## Introduction

* "A Web Implementation of Lexicon Experience Language"
* CSS based on Bootstrap 4 (4.3.1 in DXP 7.2.x; >= 4.4.1 in DXP 7.3.x)
* JS Components built with React (Liferay 7.3)
* Clay 3 with Liferay 7.3, Clay 2 with Liferay 7.2

.footnote[
  https://next.clayui.com/
]

---

# Clay

## How to Use Clay?

* Install with NPM or Yarn
* Install via Clay CSS CDN

.footnote[
  https://next.clayui.com/docs/get-started/how-to-use-clay.html
]

---

# Clay

## Clay Taglib

### Consistent markup in JSPs

```jsp
<%@ taglib uri="http://liferay.com/tld/clay" prefix="clay" %>
```

### Available in Freemarker templates as well

```Freemarker
<@clay["image-card"]
    imageSrc="${blogEntry.getCoverImageURL(themeDisplay)}"
    href="${viewURL}"
    title="${entryTitle}"
    subtitle="${blogEntry.getDisplayDate()?date}"/>
```
---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks
1. .active[Page Layouts]
1. Web-Content Templates
1. Widget Display Templates
1. Theme Context Contributor
1. Theme Contributor
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Page Layouts]

.bottom-bar[
  {{title}}
]

---

# Page Layouts

## Overview

* TODO

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks
1. Page Layouts
1. .active[Web-Content Templates]
1. Widget Display Templates
1. Theme Context Contributor
1. Theme Contributor
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Web-Content Templates]

.bottom-bar[
  {{title}}
]

---

# Web-Content Templates

## Overview

* TODO

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks
1. Page Layouts
1. Web-Content Templates
1. .active[Widget Display Templates]
1. Theme Context Contributor
1. Theme Contributor
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Widget Display Templates]

.bottom-bar[
  {{title}}
]

---

# Widget Display Templates

## Overview

- Lightweight markup customization of Liferay's core applications
- Implemented with Freemarker templates
- Available for set based widgets, e.g. *Asset-Publisher*, *Blogs*, *Breadcrumb*, etc.
- Also available for custom applications

---

# Widget Display Templates

## Available Variables

* TODO

---

# Widget Display Templates

## Exercise: Implement a Bootstrap Carousel

* TODO

---

# Widget Display Templates

## Exercise: Configure a Lightdesk With Cards

* TODO
