title: Development with Liferay 
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
1. .active[Liferay Workspace]
1. Docker Setup
1. DXP Source Access
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Liferay Workspace]

.bottom-bar[
  {{title}}
]

---

# Liferay Workspace

## Introduction

1. Available both for Maven and Gradle

---

# Liferay Workspace

## Target Platform configuration

1. TODO

.footnote[
  See:

  https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins-target-platform

  https://liferay.dev/blogs/-/blogs/what-is-the-target-platform-

  https://github.com/rotty3000/papersntalks/blob/master/2020/Liferay-Workspace-DXP.md
]

---

# Liferay Workspace

## Tips and Tricks

### How do I determine valid target.platform values?

See: https://repository.liferay.com/nexus/content/repositories/liferay-public-releases/com/liferay/portal/release.dxp.bom/

---

# Liferay Workspace

## Tips and Tricks

### How do I determine the bundle version applied for a particular target.platform?

e.g. which version of JUnit is used?

inspect third.party BOMs at https://repository.liferay.com/nexus/content/repositories/liferay-public-releases/com/liferay/portal/release.dxp.bom.third.party/

for javax.\* and osgi.\* see:

https://repository.liferay.com/nexus/content/repositories/liferay-public-releases/com/liferay/portal/release.dxp.bom.compile.only/

---

# Liferay Workspace

## Tips and Tricks

### deployFast task

speed up deployment times for WAR based projects

.footnote[
https://loop.liferay.com/home/-/loop/feed/19825955
]

---

# Liferay Workspace

## Fix JAVA_HOME issues in Developer Studio DXP on Windows

1. `org.gradle.java.home=C:/Program Files/Java/your_jdk_version` - _Note the forward slashes on Windows._

.footnote[
  https://discuss.gradle.org/t/specifying-jre-in-eclipse-using-buildship-does-not-work/21474
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. .active[Docker Setup]
1. DXP Source Access
]

---

title: Development with Liferay 
layout: true

###.breadcrumbs[Development with Liferay › Docker Setup]

.bottom-bar[
  {{title}}
]

---

# Docker Setup 

## Overview

* Introduction and Features

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Docker Setup
1. .active[DXP Source Access]
]

---

title: Development with Liferay 
layout: true

###.breadcrumbs[Development with Liferay › DXP Source Access]

.bottom-bar[
  {{title}}
]

---

# DXP Source Access 

* DXP Sources are accesible at: [https://github.com/liferay/liferay-dxp](https://github.com/liferay/liferay-dxp) 
* Tags for all Fix- and Service Packs
* Access instructions at: [https://help.liferay.com/hc/en-us/articles/360045389291-Liferay-DXP-Source-Code-Access](https://help.liferay.com/hc/en-us/articles/360045389291-Liferay-DXP-Source-Code-Access)
