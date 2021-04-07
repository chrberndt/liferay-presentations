title: Integrating with the Asset Framework 
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---

class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Backend Development 

# {{title}}

christian.berndt@liferay.com

.date[
  Wien, 23 März 2022
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Concepts and Terms]
1. Implementation Steps
]

---

title: Concepts and Terms 
layout: true

###.breadcrumbs[Asset Framework › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms

## Asset

* A generic way to refer to any type of content stored in and managed by Liferay 

## AssetEntry

* A generic representation of an entity stored and managed by Liferay, e.g. 
  * Web Content Article
  * Wiki Page
  * Blogs Post
  * File 

.footnote[
https://help.liferay.com/hc/en-us/articles/360034474752-Assets-Integrating-with-Liferay-s-Framework
]

---

# Concepts and Terms

## Asset Framework

* A set of common capabilities for different types of Assets, e.g. 
  * Tags and categories
  * Comments and ratings

---

class: agenda

# .inner[Asset Framework]

.items[
1. Concepts and Terms
1. .active[Implementation Steps]
]

---

title: Implementation Steps 
layout: true

###.breadcrumbs[Asset Framework › Implementation Steps]

.bottom-bar[
  {{title}}
]

---

# Implementation Steps

## Overview

1. Enable Assets at Service Layer
1. Implement AssetRenderers

---

# Implementation Steps 

## Enable Assets at Service Layer 

1. Enable the respective AssetFramework services in `service.xml`
1. Add status finders in `service.xml`
1. In your <Entity>LocalServiceImpl.java add, update, and delete AssetEntries in the respective \*LocalService methods

---

# Implementation Steps

## Implement AssetRenderers 

1. AssetRenderer
1. AssetRendererFactory
