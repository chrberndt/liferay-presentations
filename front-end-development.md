title: Liferay Front-End Development
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---

class: impact

# {{title}}
christian.berndt@liferay.com

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Front-End Development Tasks]
1. Tools and Frameworks
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Front-End Development Tasks]

.bottom-bar[
  {{title}}
]

---

# Front-End Development Tasks

## Overview

* Theme Development
* Page Layouts
* Web-Content Templates
* Widget Templates
* Fragments
* Client-Side Javascript Widgets

---

# Available Strategies

## Liferay (OSGi) Modules

* Themes
* Client-JS Widgets

## Templates

* Web-Content Templates
* Widget Templates

## Fragments

* Reusable Bundles of HTML, CSS, and JS code

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Front-End Development Tasks
1. .active[Tools and Frameworks]
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Tools and Frameworks]

.bottom-bar[
  {{title}}
]

---

# Tools and Frameworks

## Introduction

1. liferay-js-themes-toolkit
1. Gradle Theme Project
1. Maven Theme Project
1. liferay-js-toolkit

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Front-End Development Tasks
1. Tools and Frameworks
1. .active[Theme Development]
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Theme Development]

.bottom-bar[
  {{title}}
]

---

# Theme Development

## Theme Development Tasks

* Implement responsive markup
* Configure brand logo, fonts, and colors
* Provide default page layouts
* Using Javascript

---

# Theme Development

## Guidelines, Frameworks, and Tools

* Freemarker
* Lexicon
* Clay
* liferay-js-themes-toolkit
* `blade create -t theme -v 7.2 my-liferay-theme`

.footnote[
* https://liferay.design/lexicon/
* https://github.com/liferay/liferay-js-themes-toolkit
]

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
* CSS based on Bootstrap 4
* JS Components built with React (Liferay 7.3)

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

# liferay-js-themes-toolkit

## Introduction

* A set of NPM packages
* Designed to create, update, and maintain Liferay Themes

## Most relevant packages

* __generator-liferay-theme__: A Yeoman generator for creating themes, themelets, and layout templates
* __liferay-theme-tasks__: A set of Gulp tasks for building and deploying themes

## Supported Node Version

__10.15.1__ with Liferay __7.2.x__

.footnote[
  https://github.com/liferay/liferay-js-themes-toolkit

  https://github.com/liferay/liferay-js-themes-toolkit/issues/407
]

---

# liferay-js-themes-toolkit

## Install Liferay Locally

1. Unpack the bundle
1. Enable `developer-properties` in `$LIFERAY_HOME/portal-ext.properties`
1. Startup Liferay with `$LIFERAY_HOME/$TOMCAT_HOME/bin/catalina.sh run`
1. Deploy the license file

---

# liferay-js-themes-toolkit

## Install Yeoman

`sudo npm install -g yo`

## Update Installed Generators with `yo`

```
berndt@x270$ yo
? 'Allo Christian! What would you like to do?
  Liferay Bundle
  Liferay Js
  ──────────────
❯ Update your generators
  Install a generator
  Find some help
  Get me out of here!
(Move up and down to reveal more choices)
```

---

# liferay-js-themes-toolkit

## Create a Theme Project with `yo`

```
berndt@x270:git$ yo liferay-theme liferay-simple-theme


Welcome to the splendid Themes SDK generator!


ℹ️ This version of the Themes SDK (9.5.0) supports Liferay DXP
and Portal CE from 7.2 to 7.3.

For older versions, please use v8 of the toolkit:

> npm install -g generator-liferay-theme@^8.0.0 ↩
> yo liferay-theme:app ↩


? What would you like to call your theme? Liferay Simple Theme
? What id would you like to give to your theme? liferay-simple-theme
? Which version of Liferay is this theme for? 7.2
? Would you like to add Font Awesome to your theme? Yes
 conflict .gitignore
? Overwrite .gitignore? overwrite
    force .gitignore
   create gulpfile.js
   create package.json
   create src/WEB-INF/liferay-look-and-feel.xml
   create src/WEB-INF/liferay-plugin-package.properties
   create src/images/thumbnail.png
   create src/css/_custom.scss

```
---

# liferay-js-themes-toolkit

## Create a Theme Project with `yo` (continued)

```
...
✔️ The project has been created successfully.

ℹ️ Now we will invoke gulp init for you, to configure your deployment
strategy.

Remember, that you can change your answers whenever you want by
running gulp init again.

? Select your deployment strategy Local App Server
? Enter the path to your app server directory: /home/berndt/liferay-front-end-7.2.0.3/bundles/tomcat-9.0.17
? Enter the url to your production or development site: http://localhost:8080
```

---

# Blade Theme Project

.col-6[
## Theme Project Initialization

```
blade create -t theme -v 7.2 my-liferay-theme
```
]

.col-6[
## Initial Project Structure

```
my-liferay-theme/
├── build.gradle
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
└── src
    └── main
        ├── resources
        │   └── resources-importer
        │       └── sitemap.json
        └── webapp
            ├── css
            │   └── _custom.scss
            └── WEB-INF
                ├── liferay-plugin-package.properties
                └── web.xml
```
]
---


# Providing Sample Content

## Resources Importer

* TODO

## Site Initializer

* TODO

---

# Implement Responsive Markup

## Freemarker

.col-6[
  TODO: Insert Diagram
]

.col-6[
* Template language to generate text output based on templates and changing data
* Data provided either as Java or XML object
]

.footnote[
  https://freemarker.apache.org
]

---

# Implement Responsive Markup

## Freemarker Usage in Liferay

* Theme Templates
* Layout Templates
* Web-Content Templates
* Widget Display Templates
* Email Notification Templates

---

# Implement Responsive Markup

## `portal_normal.ftl`

.col-6[

]

---

# Configure brand logo, fonts, and colors

##

---

# Provide default page layouts

---

# Using Javascript




---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Front-End Development Tasks
1. Tools and Frameworks
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. .active[Fragment Development]
1. Client-Side JS Widgets
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Fragment Development]

.bottom-bar[
  {{title}}
]

---

# Fragment Development

## Introduction

* Introduced in Liferay 7.1
* ...

---

# Fragment Development

## Fragment Use Cases

* Keyvisuals
* Call to action
* Testimonials
* Event and campaign teasers
* Customizable carousels

---
class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Front-End Development Tasks
1. Tools and Frameworks
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. .active[Client-Side JS Frameworks]
]

---

title: Liferay Front-End Development
layout: true

###.breadcrumbs[Liferay Front-End Development › Client Side JS Frameworks]

.bottom-bar[
  {{title}}
]

---

# Client Side JS Frameworks

## Introduction

* Adapt scripts available for all major frameworks (REACT, Angular, Vue.js)
* ...

---

# Client Side JS Frameworks

## Challenges

* Limited Control of the DOM
* Client-Side Routing
* Interoperation with Liferay JS
* Coexistence with other frameworks on the page (Senna, jQuery, ...)
* Multiple React/Angular/Vue applications on one page
* Multiple instances of the same app on one page

