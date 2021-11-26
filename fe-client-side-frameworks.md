title: Client Side Frameworks 
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---
class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Client Side Frameworks 

# {{title}}

christian.berndt@liferay.com

.date[
  Vienna, 20 November 2021
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Overview]
1. React 
1. Angular
1. VueJS
]

---

title: Client Side Frameworks 
layout: true

###.breadcrumbs[Client Side Frameworks › Overview]

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

---

# Client Side JS Frameworks

## Examples Provided by Liferay

* https://liferay.github.io/liferay-frontend-projects/

---

class: agenda

# .inner[Client Side Frameworks]

.items[
1. Overview
1. .active[React] 
1. Angular
1. VueJS
]

---

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › React]

.bottom-bar[
  {{title}}
]

---

# React 

## Overview

* Tooling
* Creating a Liferay React Widget Module
* Embedding a React Component in JSP
* Using Clay Components

---

# Tooling

* `yarn` - make sure to use `yarn` to manage your npm dependencies, see: [https://liferay.dev/blogs/-/blogs/liferay-gradle-yarn-workspaces](https://liferay.dev/blogs/-/blogs/liferay-gradle-yarn-workspaces)
* `deployFast` (see: https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task)

.footnote[
  [https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task](https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task)
]

---

# Creating a Liferay React Widget Module

1. Create a React app with `create-react-app`

  ```bash
  npx create-react-app my-app
  ```
1. Adapt the React app to Liferay with `yo liferay-js:adapt`

  ```bash
  yo liferay-js:adapt
  ```

.footnote[
1. [https://create-react-app.dev](https://create-react-app.dev)
1. [https://github.com/liferay/liferay-frontend-projects/blob/master/maintenance/projects/js-toolkit/docs/How-to-adapt-most-popular-frameworks-projects.md](https://github.com/liferay/liferay-frontend-projects/blob/master/maintenance/projects/js-toolkit/docs/How-to-adapt-most-popular-frameworks-projects.md)
]

---

# Example: Retrieve a List of Blog Posts

* See: [https://github.com/lgdd/lfug20-react-workshop#lfug-20-meetup--react-workshop](https://github.com/lgdd/lfug20-react-workshop#lfug-20-meetup--react-workshop)

---

# Embedding a React Component in JSP

## Intrdocution

* A common paradigm in Liferay frontend development
* Useful, for example, to customize default components

---

# Embedding a React Component in JSP

## Implementation Steps

1. Create a Liferay Module Project of type `mvc-portlet`
1. Configure `Web-ContextPath` in `bnd.bnd`
1. Include resources created by `packageRunBuild` into module (`bnd.bnd`)
1. Configure JS dependencies in `package.json` (name attribute must match Web-ContextPath in `bnd.bnd`)
1. Implement React Component
1. Use `<react:component />` tag to render the component within your JSP

---

# Using Clay Components

## Introduction

* Clay: a set of React based components created and maintained by Liferay
* Usable in custom React components embedded in JSP
* TODO: usable in standalone widgets based on React?

---

class: agenda

# .inner[Client Side Frameworkst]

.items[
1. Overview
1. React
1. .active[Angular]
1. VueJS
]

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › Angular]

.bottom-bar[
  {{title}}
]

---

# Angular 

## Overview

* TODO

---

class: agenda

# .inner[Client Side Frameworks]

.items[
1. Overview
1. React
1. Angular
1. .active[VueJS]
]

---

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › VueJS]

.bottom-bar[
  {{title}}
]

---

# VueJS 

## Overview

* TODO

