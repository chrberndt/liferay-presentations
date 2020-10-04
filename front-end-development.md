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
1. .active[Customizing Liferay's UI]
1. Frameworks and Tools
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
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
* Page Layouts
* Web-Content Templates
* Widget Display Templates
* Fragments
* Client-Side Javascript Widgets
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
1. .active[Frameworks and Tools]
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

###.breadcrumbs[Liferay Front-End Development › Frameworks and Tools]

.bottom-bar[
  {{title}}
]

---

# Frameworks and Tools

## Overview

* Lexicon
* Clay
* Freemarker
* liferay-js-themes-toolkit
* Blade CLI Theme Template
* Gradle Theme Project
* Maven Theme Project
* liferay-js-toolkit

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
# liferay-js-themes-toolkit

## Overview

- Based on *GulpJS*,\* a JavaScript taskrunner
- Based on *Yeoman*,\*\* a Javascript project generator
- `watch` functionality provided by `gulp watch`
- Available for Liferay 7.0.x, 7.1.x, 7.2.x

.footnote[
\* https://gulpjs.com

\*\* https://yeoman.io
]

---

# liferay-js-themes-toolkit

## Prerequisities

* `node -v` > 8.0.0
* Yeoman `npm install -g yo`

## Installation

  ```bash
  npm install -g generator-liferay-theme@^9.x.x
  ```
---

# Frameworks and Tools

## Liferay Developer Studio

1. Create a *Liferay Workspace Project* (or use an existing one):
  ```
  File > New > Liferay Workspace Project
  ```
1. Create a new *Liferay Module Project*:
  ```
  File > New > Liferay Module Project
  ```
1. Choose *theme* as Project Template:
  ```
  Project Template Name: theme
  ```
1. The project will be created in the Liferay Workspace's `wars` directory

---

# Frameworks and Tools

## Blade CLI Theme Template

### Prerequisities

```bash
blade version > 3.5.0
```

### Create a *Liferay Theme Project* with BLADE

```bash
blade create -t theme my-blade-theme
```
---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks and Tools
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

* Setup your development environment
* Implement responsive markup
* Define styles for logo, images, fonts, and colors
* Provide default page layouts
* Using Javascript
* Make the theme configurable
* Creating reusable themelets
* Using Stylebooks

---

# Setup Your Development Environment

## Install Liferay Locally

1. Unpack the bundle
1. Enable `developer-properties` in `$LIFERAY_HOME/portal-ext.properties`
1. Adjust `user.timezone` setting in `TOMCAT_HOME/bin/setenv.sh / .bat`
1. Startup Liferay with `$LIFERAY_HOME/$TOMCAT_HOME/bin/catalina.sh run`
1. Deploy the license file
1. Navigate to `http://localhost:8080` and finish the setup wizard

---

# Setup Your Development Environment

## Use a Liferay Cloud Setup

* TODO

---

# Setup Your Development Environment

## portal-developer.properties

```properties
schema.module.build.auto.upgrade=true

theme.css.fast.load=false
theme.css.fast.load.check.request.parameter=true
theme.images.fast.load=false
theme.images.fast.load.check.request.parameter=true

javascript.fast.load=true
javascript.log.enabled=false

layout.template.cache.enabled=false

browser.launcher.url=

combo.check.timestamp=true

minifier.enabled=false

module.framework.properties.initial.system.check.enabled=true
module.framework.properties.osgi.console=localhost:11311

com.liferay.portal.servlet.filters.cache.CacheFilter=false
com.liferay.portal.servlet.filters.etag.ETagFilter=false
com.liferay.portal.servlet.filters.header.HeaderFilter=false
com.liferay.portal.servlet.filters.themepreview.ThemePreviewFilter=true
```

---

# Setup Your Development Environment

## Install Yeoman

```bash
sudo npm install -g yo
```

## Update Installed Generators with `yo`

```bash
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

# Create, Build, and Deploy a Theme

## Overview

1. Generate the Theme Project with *Yeoman*
1. Build the theme with Gulp
1. Override files in the `build` directory with corresponding files in the `src` directory
1. Deploy the theme to the server
1. Configure the theme for the default site of your development server
1. Use `gulp watch` to automatically refresh the theme when you modify the sources

---

# Create, Build, and Deploy a Theme

## Create a Theme Project with Yeoman (`yo`)

```bash
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
   create gulpfile.js
   create package.json
   create src/WEB-INF/liferay-look-and-feel.xml
   create src/WEB-INF/liferay-plugin-package.properties
   create src/images/thumbnail.png
   create src/css/_custom.scss

```
---

# Setup Your Development Environment

## Create a Theme Project with `yo` (continued)

```bash
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

# liferay-js-themes-toolkit

## Anatomy of a Liferay Theme

```bash
liferay-simple-theme/
├── .gitignore
├── gulpfile.js
├── LICENSE
├── liferay-theme.json
├── package.json
├── package-lock.json
├── README.md
└── src
    ├── css
    │   └── _custom.scss
    ├── images
    │   └── thumbnail.png
    └── WEB-INF
        ├── liferay-look-and-feel.xml
        └── liferay-plugin-package.properties
```
---

# liferay-js-themes-toolkit

## Anatomy of a Liferay Theme: `gulpfile.js`

.col-6[
```js
/**
 * © 2017 Liferay, Inc. <https://liferay.com>
 *
 * SPDX-License-Identifier: MIT
 */

'use strict';

var gulp = require('gulp');
var liferayThemeTasks = require('liferay-theme-tasks');

liferayThemeTasks.registerTasks({
  gulp,
});
```
]

.col-6[
* Automatically loaded when you run the `gulp` command.
* Registers the functions exported by `liferay-theme-tasks` into gulp's task system
* Available `liferay-theme-tasks`: *build, deploy, extend, kickstart, status, watch, init*
* For a complete list of tasks run `gulp help`
]

.footnote[
https://github.com/liferay/liferay-js-themes-toolkit/tree/master/packages/liferay-theme-tasks
]

---

# liferay-js-themes-toolkit

## Anatomy of a Liferay Theme: `liferay-theme.json`

.col-6[
```json
TODO
```
]

.col-6[
* Local project settings
* Excluded from `git` by default
]

---

# liferay-js-themes-toolkit

## Anatomy of a Liferay Theme: `package.json`

.col-6[
```json
TODO
```
]

.col-6[
* NPM project and dependency configuration
]

---

# liferay-js-themes-toolkit

## Anatomy of a Liferay Theme: `src`

.col-6[
```bash
TODO
```
]

.col-6[
* Core theme files
* Files stored in `src` overwrite files from __\_unstyled__ and __\_styled__ during build
]

---

# liferay-js-themes-toolkit


.col-6[
## The `_unstyled` Theme

* TODO

]

--

.col-6[
## The `_styled` Theme

* TODO

]

---

# liferay-js-themes-toolkit

## The Theme Build Process: `gulp build`

1. Base theme (`_styled`) files are copied to the `build` directory
1. Theme files from `src` are copied to the `build` directory
  > In order to override base theme files, your custom files must have the same names and directory structure as the files you want to customize.
1. If necessary, JS and SCSS files are merged and compiled
1. The Theme is packaged as WAR file and stored in the `dist` folder

---

# Blade Theme Project

.col-6[
## Theme Project Initialization

```bash
blade create -t theme -v 7.2 my-liferay-theme
```
]

.col-6[
## Initial Project Structure

```bash
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

# Customize Theme Templates

## Theme template files of the base theme are found in `build/templates`

.small[
|      Template       | &nbsp; |  Function |
| ------------------- |-| --------- |
| `portal_normal.ftl` | | template for a regular portal page (with banner-, content-, and footer-sections) |
| `portal_pop_up.ftl` | | template for a portal page in pop-up mode (without banner- and footer-section) |
| `portlet.ftl`       | | template for common portlet markup |
| `navigation.ftl`    | | template for the main navigation |
| `init.ftl`          | | setup common variables, included by `portal_normal.ftl`, `portal_pop_up.ftl` |
| `init_custom.ftl`   | | default extension point for custom template initialization code  |
]

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

## Freemarker

### An Example

TODO: https://freemarker.apache.org/docs/dgui_template_overallstructure.html

### Directives and Expressions

TODO: https://freemarker.apache.org/docs/dgui_template_directives.html

TODO: https://freemarker.apache.org/docs/dgui_template_exp.html

### Using Taglibs

TODO: Show how to use the clay-taglib in FTL

### Using Macros

---

# Implement Responsive Markup

## Key Sections of `portal_normal.ftl`

.col-6[

]

.col-6[
]


.footnote[
  https://github.com/liferay/liferay-portal/blob/7.2.x/modules/apps/frontend-theme/frontend-theme-unstyled/src/main/resources/META-INF/resources/_unstyled/templates/portal_normal.ftl
]

---

# Implement Responsive Markup

## Markup Implementation Tasks

* Implement logo and brand
* Implement a responsive navigation
* Implement a footer

> Note: when using `gulp watch` template modifications <br/> might need take some to be reflected in the portal.

---

# Configure Brand Logos, Images, Fonts and Colors

## Overview

* SASS
* Include Clay / Bootstrap Styles
* Customize Clay / Bootrap Variables
* Override Clay / Bootstrap Styles
* Implement Custom Styles with SASS

---

# Configure Brand Logos, Images, Fonts and Colors

## SASS

.col-6[
### SCSS source

```scss
#header {
  h1 {
    color: blue;
  }
}

#content {
  h1 {
    color: darkgrey;
  }
}
```
]

.col-6[
### Compiled CSS
```css
#header h1 {
  color: blue;
}

#content h1 {
  color: darkgrey;
}
```
]

# &nbsp;

.col-6[
### Markup
```html
<header id="header">
  <h1>This is a header headline></h1>
</header>
<section id="content">
  <h1>This is a content headline></h1>
</section>
```
]

.col-6[
### Rendered Output
<h1 style="color: blue; font-family: serif;">This is a header headline</h1>
<h1 style="color: darkgrey; font-family: serif;">This is a content headline</h1>
]

.footnote[
https://sass-lang.com/
]

---

# Configure Brand Logos, Images, Fonts and Colors

## Using Clay / Bootstrap Styles in Markup

### `clay.css` included by default in themes based on the `_styled` theme

```html
<link class="lfr-css-file"
      data-senna-track="temporary"
      href="http://localhost:8080/o/liferay-simple-theme/css/clay.css?browserId=other&amp;themeId=liferaysimpletheme_WAR_liferaysimpletheme&amp;..."
      id="liferayAUICSS"
      rel="stylesheet"
      type="text/css" />
```
> <small>href attribute abbreviated for clarity.</small>

.col-6[

### Using Bootstrap CSS classes

```html
<div class="alert alert-primary" role="alert">
  A simple primary alert-check it out!
</div>
```
]

.col-6[
### Rendered Output
<style>
.alert {
  position: relative;
  padding: .75rem 1.25rem;
  margin-bottom: 1rem;
  border: 1px solid transparent;
  border-radius: .25rem;
  font-size: 1rem;
}

.alert-primary {
    color: #004085;
    background-color: #cce5ff;
    border-color: #b8daff;
}
</style>

<div class="alert alert-primary" role="alert">
  A simple primary alert-check it out!
</div>
]

---

# Configure Brand Logos, Images, Fonts and Colors

## Using the Clay Taglib

.col-6[

### Clay Tag

```Freemarker
<@clay["alert"]
  title="Info: "
  message="A simple clay alert-check it out!"/>
```
]

.col-6[
### Rendered Markup
```html
<div class="alert alert-info fade show" id="ehhg" role="alert">
  <span class="alert-indicator">
    <svg class="lexicon-icon lexicon-icon-info-circle"
         focusable="false"
         role="presentation" viewBox="0 0 512 512">
      <path class="lexicon-icon-outline" d="..."></path>
    </svg>
  </span>
  <strong class="lead">Info: </strong>A simple clay alert-check it out!
</div>
```
> <small> Path definition parameters removed for clarity. </small>
]

.col-6[
### Rendered Output
<style>
.alert, .portlet-msg-alert, .portlet-msg-error, .portlet-msg-help, .portlet-msg-info, .portlet-msg-progress, .portlet-msg-success {
    border-style: solid;
    display: block;
    word-wrap: break-word;
}
.alert-info, .portlet-msg-help, .portlet-msg-info, .portlet-msg-progress {
    color: #0c5460;
    background-color: #d1ecf1;
    border-color: #bee5eb;
}
.alert-indicator {
    font-size: 1.25rem;
}
.lexicon-icon {
    display: inline-block;
    fill: currentColor;
    height: 1em;
    margin-top: -3px;
    vertical-align: middle;
    width: 1em;
}
.alert-indicator + .lead {
    margin-left: 0.3125rem;
}
.lead {
    font-size: 1.25rem;
    font-weight: 300;
}
</style>
<div class="alert alert-info fade show" id="ehhg" role="alert"><span class="alert-indicator"><svg class="lexicon-icon lexicon-icon-info-circle" focusable="false" role="presentation" viewBox="0 0 512 512">
  <path class="lexicon-icon-outline" d="M437,75C388.7,26.6,324.4,0,256,0C187.6,0,123.3,26.6,75,75C26.6,123.3,0,187.6,0,256c0,68.4,26.6,132.7,75,181c48.4,48.4,112.6,75,181,75c68.4,0,132.7-26.6,181-75c48.4-48.4,75-112.6,75-181C512,187.6,485.4,123.3,437,75z M288,384c0,17.7-14.3,32-32,32c-17.7,0-32-14.3-32-32V224c0-17.7,14.3-32,32-32c17.7,0,32,14.3,32,32V384z M256,160c-17.7,0-32-14.3-32-32c0-17.7,14.3-32,32-32s32,14.3,32,32C288,145.7,273.7,160,256,160z"></path>
</svg></span><strong class="lead">Info: </strong>A simple clay alert-check it out!</div>
]

---

# Configure Brand Logos, Images, Fonts and Colors

## Using Images, Icon Libraries, and Vector Graphics

* Using Images
* Using Icon Libraries (Fontawesome)
* Using Vector Graphics

---

# Provide Custom Page Layout

## Layouts Provided OOTB

* TODO

## Providing Custom Page Layouts

* As part of a theme
* As a separate module

---

# Using Javascript

## Javascript Tasks

* Using vanilla JS
* Using libraries provided by Liferay OOTB
* Adding third party JS libraries

---

# Using Javascript

## Libraries Provided OOTB

* jQuery (enabled in 7.2, disabled by default in 7.3.x, see note 1)
* Metal.js

## Disabled Libraries

* Lodash (OOTB in 7.1, disabled by default in 7.2)

.footnote[
  1) https://liferay.dev/blogs/-/blogs/jquery-is-disabled-long-live-jquery
]

---

# Using Javascript

## Libraries Provided OOTB

```html
<link charset="utf-8" data-senna-track="permanent" href="/o/frontend-theme-font-awesome-web/css/main.css" rel="stylesheet">
<script data-senna-track="permanent" src="/combo?browserId=other&minifierType=js&languageId=en_US&b=7210&t=1580975323481&\
  /o/frontend-js-jquery-web/jquery/jquery.min.js&\
  /o/frontend-js-jquery-web/jquery/bootstrap.bundle.min.js&\
  /o/frontend-js-jquery-web/jquery/collapsible_search.js&\
  /o/frontend-js-jquery-web/jquery/fm.js&\
  /o/frontend-js-jquery-web/jquery/form.js&\
  /o/frontend-js-jquery-web/jquery/popper.min.js&\
  /o/frontend-js-jquery-web/jquery/side_navigation.js" type="text/javascript"></script>
```

---

# Make the Theme Configurable

## Implementation Steps

1. Define settings in `liferay-look-and-feel.xml`
1. Retrieve settings in Freemarker templates, e.g. `init_custom.ftl`
1. Render markup according to settings

---

# Make the Theme Configurable

.col-6[
## liferay-look-and-feel.xml

```xml
<settings>
  <setting configurable="false"
           key="color-palette"
           value="primary,success,danger,warning,...,white" />
  <setting configurable="true"
           key="show-footer"
           type="checkbox" value="true" />
  <setting configurable="true"
           key="show-header"
           type="checkbox" value="true" />
  <setting configurable="true"
           key="show-header-search"
           type="checkbox" value="true" />
  <setting configurable="true"
           key="show-maximize-minimize-application-links"
           type="checkbox" value="false" />
  <setting configurable="false"
           key="show-site-name-default"
           value="true" />
  <setting configurable="false"
           key="show-site-name-supported"
           value="true" />
  <setting configurable="true"
           key="wrap-widget-page-content"
           type="checkbox" value="true" />
</settings>
```
]

.col-6[
## Rendered UI

* TODO: Add screenshot
]

---

# Make the Theme Configurable

.col-6[
## init_custom.ftl
```freemarker
<#assign
  show_footer = getterUtil
    .getBoolean(themeDisplay.getThemeSetting("show-footer"))

  show_header = getterUtil
    .getBoolean(themeDisplay.getThemeSetting("show-header"))
/>
```
]

.col-6[
## portal_normal.ftl
```freemarker
TODO
```
]

---

# Make the Theme Configurable

## Setting Attributes

|         |     |                |
| ------- | --- | -------------- |
| __key__ |     | the setting's key |
| __value__ |   | the setting's value |
| __configurable__ | &nbsp;&nbsp;&nbsp;  | whether the setting is configurable from the user interface at runtime |
| __type__ |   |  designate whether the HTML input for the setting is a *checkbox*, *select*, *text*, or *textarea* |
| __options__ |  | a comma delimited list to specify the options for the HTML input |

.footnote[
http://www.liferay.com/dtd/liferay-look-and-feel_7_2_0.dtd
]

---

# Creating Reusable Themelets

## Themelet Use Cases

* Reusable animations or effects

---

# Creating Reusable Themelets

## Development Steps

1. Create the themelet with `yo liferay-theme:themelet`
1. Implement themelet code in the `src` directory
1. Link the themelet to your local NPM repository with `npm link .` (in the themelet's root directory)
1. Use the themelet in other themes by running `gulp extend`

---

# Creating Reusable Themelets

## Generated Themelet Dependencies

Extending a themelet will add a themelet dependency like the following to your theme's `package.json`:

```json
...
"liferayTheme": {
  "baseTheme": "styled",
  "fontAwesome": true,
  "screenshot": "",
  "templateLanguage": "ftl",
  "version": "7.2",
  "themeletDependencies": {
    "widget-dropzone-themelet": {
      "liferayTheme": {
        "screenshot": "",
        "themelet": true,
        "version": "7.2"
      },
      "name": "widget-dropzone-themelet",
      "version": "1.0.0",
      "path": "/home/berndt/.npm-global/lib/node_modules/widget-dropzone-themelet"
    }
  }
},
...
```
---

# Creating Reusable Themelets

## Themelet-Include During Build

* Copies of referenced themelets are stored the main theme's `themelets` directory
* A reference to the themelet's `_custom.scss` is injected between the theme's `_custom.scss` <br/> `/* inject:imports */` and `/* endinject */` comments

---

# Themes

## Stylebooks

* See: https://loop.liferay.com/home/-/loop/feed/21480522 (7.3+)

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks and Tools
1. Theme Development
1. .active[Page Layouts]
1. Web-Content Templates
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
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
1. Frameworks and Tools
1. Theme Development
1. Page Layouts
1. .active[Web-Content Templates]
1. Widget Display Templates
1. Fragment Development
1. Client-Side JS Widgets
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
1. Frameworks and Tools
1. Theme Development
1. Page Layouts
1. Web-Content Templates
1. .active[Widget Display Templates]
1. Fragment Development
1. Client-Side JS Widgets
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

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks and Tools
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
* Content Pages support Workflows
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

# Fragment Development

## Using Freemarker

* Freemarker supported: https://issues.liferay.com/browse/LPS-95736
* Requires alternative Freemarker syntax, see: https://freemarker.apache.org/docs/dgui_misc_alternativesyntax.html

.footnote[
  https://help.liferay.com/hc/en-us/articles/360028726832-Page-Fragments
]
---

# Fragment Development

## Using Freemarker: An Example

* TODO

---
# Fragment Development

## Manage Style Settings (7.3+)

* See: https://loop.liferay.com/home/-/loop/feed/21482877

---

class: agenda

# .inner[Liferay Front-End Development]

.items[
1. Customizing Liferay's UI
1. Frameworks and Tools
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

