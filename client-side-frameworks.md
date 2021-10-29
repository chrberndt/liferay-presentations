title: Liferay Client-Side Javascript Development 
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
1. .active[Tools and Strategies]
1. liferay-js-toolkit
]

---

title: Client-Side Javascript Development
layout: true

###.breadcrumbs[Client-Side Javascript Development › Tools and Strategies]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Client-Side Javascript Development]

.items[
1. Tools and Strategies
1. .active[liferay-js-toolkit]
]

---

title: Client-Side Javascript Development
layout: true

###.breadcrumbs[Client-Side Javascript Development › liferay-js-toolskit]

.bottom-bar[
  {{title}}
]

---

# liferay-js-toolkit

## Overview

* General Concepts
* Setup liferay-js-toolkit
* Creating a React Widget

.footnote[
https://github.com/liferay/liferay-js-toolkit
]

---

# General Concepts

* TODO

---

# Setup liferay-js-toolkit

## Prerequisities

1. `node -v 10.15.1`
1. `npm install -g yo` (yo@3.1.1 at the time of writing)
1. `npm install -g generator-liferay-js` (generator-liferay-js@2.18.2 at the time of writing)

---

# Creating a React Widget

## Development Environment

* Liferay 7.3.0 CE GA1
* Node 10.15.1

---

# Creating a React Widget

## Setup Steps

1. Create a React App
1. Adapt the React App to Liferay
1. Deploy the Widget to Liferay
1. Install the Widget on a Page


---

# Creating a React Widget

## Create a React App

* TODO

.footnote[
https://create-react-app.dev/

https://github.com/liferay/liferay-js-toolkit/wiki/How-to-adapt-most-popular-frameworks-projects

https://github.com/lgdd/lfug20-react-workshop
]

---

# Creating a React Widget

## Adapt the React App to Liferay

1. Change working directory to your React app 
  ```bash
  cd liferay-react-portlet
  ```
1. Adapt React App to Liferay 
  ```bash
  yo liferay-js:adapt
  ```
  > *Yeoman* may notify you about the existence of a conflict and prompt for permission to overwrite your files.
  > Make sure to answer __'a'__ or otherwise the adaptation to *Liferay JS Toolkit* will fail.
1. Deploy `liferay-react-portlet` to you development server
  ```
  yarn run deploy:liferay
  ```
1. Install `liferay-react-portlet` on a page
