title: Content Pages and Fragments
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
  Vienna, 13 February 2023
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Introduction]
1. Using Fragments
1. Fragment Compositions
1. Developing Fragments
]

---

title: Content Pages and Fragments
layout: true

###.breadcrumbs[Content Pages and Fragments]

.bottom-bar[
  {{title}}
]

---

# Introduction

.col-5[
## Content Pages: General Concepts
* First introduced in Liferay 7.1
* Page centered content managment (in addition to Asset based)
* Composed of Fragments and / or Widgets
]

.col-1[
  &nbsp;
]

.col-6[
  .center[<img src="images/fe-content-pages-and-fragments/introduction-content-page.png" width="95%">]
]

.footnote[
  https://learn.liferay.com/dxp/7.x/en/site-building/creating-pages/building-and-managing-content-pages/content-pages-overview.html
]

???

* *First introduced in Liferay 7.1*
  * since 7.3 a level of maturity where it can in fact be considered as production ready
* *Page centered content management*
  * in a way complementary to Liferay's traditional, asset based approach to content management (Web Content Display and Asset Publisher Portlets, Web Content Articles and Document and Media Files)
* *Composed of so called Fragments*
  * easy to use page blocks which can easily be deployed to a page via drag and drop
  * Widgets (Portlets) supported as well
---

# Introduction

## Content Page Features

* View and Draft
* Inline Editing of Content
* Support for Experiences
* Support of Workflows

???

* *View and Draft*
  * Every content page has a draft mode which allows for preparing and editing page content without publishing the changes immediately (like for widget pages)
* *Inline Editing of Content*
  * provides immediate feedback to the editor and a true WYSIWYG authoring experience
* *Support for Experiences*
  * Content pages support the concept of so called "Experiences" - Liferay's term for personalized content.
  * Display specific parts of a page according to configurable criteria, e.g. Geo location, Language Settings, etc.
* *Support for Workflows*
  * Content pages can be configured to support workflows which model approval or review processes

---

# Introduction

## Fragment Examples

.col-4[
  .center[<img src="images/front-end-development/slider-fragment.png" width="95%">]
]

.col-4[
  .center[<img src="images/front-end-development/features-fragment.png" width="95%">]
]

.col-4[
  .center[<img src="images/front-end-development/highlights-fragment.png" width="95%">]
]

---

# Introduction

.col-5[

## Exercise: Hello Content Page

1. Create an empty page
1. Define the page structure by adding OOTB fragments
1. Edit page content
1. Publish the draft

]

.col-1[
  &nbsp;
]

.col-6[
  .center[<img src="images/fe-content-pages-and-fragments/introduction-hello-content-page.png" width="95%">]
]
---

# How it Works

## A Simple Example: Banner Center

```html
<div class="banner py-6 py-md-8 text-white text-break" data-lfr-background-image-id="banner">
  <div class="container my-lg-6">
    <div class="row">
      <div class="col-12 col-md-8 col-xl-6">
        <h1
*          data-lfr-editable-id="01-title"
*          data-lfr-editable-type="rich-text"
        >
          Banner Title Example
        </h1>

*        <div class="mb-4 lead" data-lfr-editable-id="02-subtitle" data-lfr-editable-type="rich-text">
          <p>
            This is a simple banner component that you can use when
            you need extra attention to featured content or
            information.
          </p>
        </div>

        <a
          class="btn btn-primary"
*          data-lfr-editable-id="03-link"
*          data-lfr-editable-type="link"
*          href=""
*          id="fragment-${fragmentEntryLinkNamespace}-03-link"
        >
          Go Somewhere
        </a>
      </div>
    </div>
  </div>
</div>
```

---

# How it Works

## A Simple Example: Banner Center

* TODO: renders as

---

# How it Works

## A Simple Example: Banner Center

* TODO: can be edited as follows

---

# Tooling

## Setup Your Environment

* Install Fragments Toolkit
* Start Liferay
* Create, Deploy, and Review Fragments

---

# Tooling

## Fragments Toolkit Capabilities

| | | |
|-|-|-|
|`yarn run add-collection`| &nbsp;&nbsp; | Add a new Fragments collection |
|`yarn run add-fragment` | | Add a new Fragment |
|`yarn run add-fragment-composition` | | Add a new Fragment composition |
|`yarn run add-page-template` | | Add a new Page Template |
|`yarn run compress`| | Assemble collection as ZIP archive |
|`yarn run export`| | Export a collection *from* Liferay |
|`yarn run import`| | Import a collection *into* Liferay |
|`yarn run import:watch`| | Import a collection *into* Liferay in watch mode |
|`yarn run preview`| | Preview Fragments |

---

# Content Pages and Fragments

.col-6[

## 1. Create a New Fragment Project

> Run `yo liferay-fragments`

```bash
berndt@x270:~$ yo liferay-fragments

    / /   /  _/ ____/ ____/ __ \/   \ \/ /
  / /    / // /_  / __/ / /_/ / /| |\  /
  / /____/ // __/ / /___/ _, _/ ___ |/ /
/_____/___/_/   /_____/_/ |_/_/  |_/_/

? Project name Sample Liferay Fragments
? Add sample content? n

Creating directory
   create src/.gitkeep
   create .editorconfig
   create .gitignore
   create package.json
   create README.md

Done!
You're ready to create fragments.
```
]

--

.col-6[

## 2. Create a New Collection

> Run `yarn run add-collection`

```bash
berndt@x270:sample-liferay-fragments$ yarn run add-collection
yarn run v1.22.5
warning package.json: No license field
$ yo liferay-fragments:collection
? Collection name (required) Custom Fragment Collection
? Collection description (optional) A collection of custom fragments
   create src/custom-fragment-collection/collection.json
Done in 49.25s.
```
]

---

# Content Pages and Fragments

.col-6[

## 3. Create a New Fragment

> Run `yarn run add-fragment`

```bash
berndt@x270:sample-liferay-fragments$ yarn run add-fragment
yarn run v1.22.5
warning package.json: No license field
$ yo liferay-fragments:fragment
? Minimum liferay version you want fragments to be compatible with (e.g. 7.3.0) 7.3.10
? Fragment name (required) Keyvisual
? Choose a collection (custom-fragment-collection)
   create src/custom-fragment-collection/keyvisual/index.html
   create src/custom-fragment-collection/keyvisual/main.js
   create src/custom-fragment-collection/keyvisual/styles.css
   create src/custom-fragment-collection/keyvisual/fragment.json
   create src/custom-fragment-collection/keyvisual/configuration.json
Done in 37.89s.
```
]

--

.col-6[

## 4. Deploy to Server

> Run `yarn run import:watch`

```bash
berndt@x270:sample-liferay-fragments$ yarn run import:watch
yarn run v1.22.5
warning package.json: No license field
$ yo liferay-fragments:import --watch
? Liferay host & port http://localhost:8080
? Username test@liferay.com
? Password [hidden]

Checking connection...
Connection successful

? Company ID liferay.com
? Group ID (Use arrow keys)
  Global
❯ Liferay DXP

```

]


---

# Content Pages and Fragments

## Anatomy of a Fragments Project

.col-6[

```bash
sample-liferay-fragments/
├── node_modules
├── package.json
├── README.md
├── src
│   └── custom-fragment-collection
│       ├── collection.json
│       └── keyvisual
│           ├── configuration.json
│           ├── fragment.json
│           ├── index.html
│           ├── main.js
│           └── styles.css
└── yarn.lock
```

| | | |
|-|-|-|
|`package.json`|&nbsp;&nbsp;| Node package configuration |
|`src`| | Sources of the fragments project |
|`yarn.lock`| | Lock file for yarn (exact versions of declared dependencies) |

]

---

# Content Pages and Fragments

## Anatomy of a Fragments Project: `package.json`

.col-9[

```json
{
  "name": "sample-liferay-fragments",
  "description": "Liferay Fragments project",
  "version": "1.0.0",

  "engines": {
    "node": ">= 8.0.0",
    "npm": ">= 6.0.0"
  },

  "keywords": [
    "liferay",
    "liferay-fragments"
  ],

  "scripts": {
    "add-collection": "yo liferay-fragments:collection",
    "add-fragment": "yo liferay-fragments:fragment",
    "add-fragment-composition": "yo liferay-fragments:fragment-composition",
    "add-page-template": "yo liferay-fragments:page-template",
    "compress": "yo liferay-fragments:compress",
    "export": "yo liferay-fragments:export",
    "import": "yo liferay-fragments:import",
    "import:watch": "yo liferay-fragments:import --watch",
    "preview": "yo liferay-fragments:preview"
  }
}
```
]

---

# Content Pages and Fragments

## Propagating Page Fragment Changes

.col-6[
### Manually Propagating Page Fragment Changes
]

.col-6[
### Automatically Propagating Page Fragment Changes
]


.footnote[
  https://learn.liferay.com/dxp/7.x/en/site-building/displaying-content/using-fragments/propagating-page-fragment-changes.html#manually-propagating-page-fragment-changes
]

---

# Content Pages and Fragments

## Anatomy of a Fragment: `configuration.json`

.col-6[
```json
{
  "fieldSets": [
    {
      "fields": [
        {
          "dataType": "int",
          "defaultValue": "3",
          "description": "number-of-slides",
          "label": "Number Of Slides",
          "name": "numberOfSlides",
          "type": "text",
          "typeOptions": {
            "validation": {
              "min": 1,
              "type": "number"
            }
          }
        },
        {
          "dataType": "object",
          "label": "text-color",
          "name": "textColor",
          "type": "colorPalette"
        }
      ]
    }
  ]
}
```
]

.col-6[
* Defined in JSON
* Supported input types:
  * checkbox
  * colorPalette
  * itemSelector
  * select
  * text
* Stored as Freemarker context object
* Processed with Freemarker
]

.footnote[
  https://learn.liferay.com/dxp/7.x/en/site-building/developer-guide/reference/fragments/fragment-configuration-types-reference.html
]

---

# Content Pages and Fragments

## Anatomy of a Fragment: `index.html`

.col-6[
* TODO: add source
]

.col-6[
* Define markup
* Define editable areas
* Process configuration
]

---

# Fragement Development

## Anatomy of a Fragment: `index.html`

### Defining Editable Areas

.col-6[
```xml
<lfr-editable id="image_id" type="image">
  <img src="placeholder.png" alt="Placeholder">
</lfr-editable>

<lfr-editable id="link_id" type="link">
  <a href="#placeholder" target="_blank">Go to placeholder</a>
</lfr-editable>

<lfr-editable id="html_id" type="html">
  <h1>Placeholder</h1>
</lfr-editable>

<lfr-editable id="text_id" type="text">Placeholder</lfr-editable>

<lfr-editable id="rich_text_id" type="rich-text">
  Placeholder
</lfr-editable>
```
]
.col-6[
```html
<!-- TODO: Process configurations with Freemarker -->
```
]

---

# Content Pages and Fragments

## Using Fragment Compositions

* TODO

.footnote[
  See: https://learn.liferay.com/dxp/7.x/en/site-building/creating-pages/building-and-managing-content-pages/building-content-pages.html#saving-a-fragment-composition
]

---

# Content Pages and Fragments

## Best Practices

* Use `${fragmentEntryLinkNamespace}` in html `id` attributes

---

# Content Pages and Fragments

## Using Freemarker

* Freemarker supported: https://issues.liferay.com/browse/LPS-95736
* Requires alternative Freemarker syntax, see: https://freemarker.apache.org/docs/dgui_misc_alternativesyntax.html

.footnote[
  https://help.liferay.com/hc/en-us/articles/360028726832-Page-Fragments
]
---

# Content Pages and Fragments

## Using Freemarker: An Example

.col-8[
```Freemarker
[#assign req = request.getRequest()]
[#assign originalRequest = portalUtil.getOriginalServletRequest(req)]

[#if originalRequest.getParameter("p_l_mode")??]
  [#if originalRequest.getParameter("p_l_mode") == "edit"]
    <a class="btn btn-lg btn-primary">Add Article</a>
  [/#if]
[/#if]
```
Display an add button only if the Content Page is in *edit* mode.
]


---
# Content Pages and Fragments

## Manage Style Settings (7.3+)

* See: https://loop.liferay.com/home/-/loop/feed/21482877

