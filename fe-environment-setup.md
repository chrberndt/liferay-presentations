title: Environment Setup 
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---
class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Liferay Front-End Development 

# {{title}}

christian.berndt@liferay.com

.date[
  Vienna, 20 November 2021
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Introduction]
1. Liferay DXP
1. Node
1. Yeoman and Liferay Theme Generator
]

---

title: Environment Setup 
layout: true

###.breadcrumbs[Environment Setup]

.bottom-bar[
  {{title}}
]

---

# Introduction 

* TODO

---

# Liferay DXP

1. Setup JDK 11
1. Setup Liferay
  1. Unzip
  1. Enable developer.properties (via portal-ext.properties)
  1. $TOMCAT_HOME/bin/catalina.sh run
  1. Deploy license key 

---

# Node

1. Install Node (preferably with n) (e.g. 14.16.1)
1. Redirect `npm -g` (if you don't use n)

---

# Setup Yeoman and Liferay Theme Generator

1. `npm install -g generator-liferay-theme@10.x.x`
1. `npm install -g yo gulp`

.footnote[
  https://learn.liferay.com/dxp/latest/en/site-building/site-appearance/themes/theme-development/getting-started/setting-up-an-environment-and-creating-a-theme.html
]
