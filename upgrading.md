title: Upgrading Liferay 
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
* .active[General Considerations]
* Liferay Upgrade Planner 
]

---

title: Upgrading Liferay 
layout: true

###.breadcrumbs[Upgrading Liferay › General Considerations]

.bottom-bar[
  {{title}}
]

---

# General Considerations 

* Upgrading Liferay Core
* Upgrading Customizations
* Upgrading Custom Components

---

class: agenda

# .inner[Upgrading Liferay]

.items[
* General Considerations
* .active[Liferay Upgrade Planner] 
]

---

title: Upgrading Liferay 
layout: true

###.breadcrumbs[Upgrading Liferay › Liferay Upgrade Planner]

.bottom-bar[
  {{title}}
]

---

# Liferay Upgrade Planner 

## Introduction

* A Plugin for Developer Studio 3.6+
* Recommended for Upgrades of Liferay > 6.2 

.footnote[
https://help.liferay.com/hc/en-us/articles/360029147451-Liferay-Upgrade-Planner
]

---

# Liferay Upgrade Planner

## Features

* Update your development environment
* Identify code affected by API changes
* TODO 

.footnote[
https://help.liferay.com/hc/en-us/articles/360029147451-Liferay-Upgrade-Planner
]

---

# Using Liferay Upgrade Planner

## Upgrade Paths

* Data Upgrade
* Code Upgrade

---

# Using Liferay Upgrade Planner

## Data Upgrade

* TODO

--- 

# Using Liferay Upgrade Planner

## Launching the Planner

1. *Project › New Liferay Upgrade Plan ...*
1. Enter a name, e.g. *Upgrade to Liferay 7.3.10*
1. Select an *Upgrade plan outline*
1. Select your *Current Liferay Version*
1. Select a *Target Liferay Version*

---

# Using Liferay Upgrade Planner

## Code Upgrade Tasks

1. Upgrade Development Environment
1. Migrade Plugins SDK Projects (Liferay 6.x)
1. Upgrade Build Dependencies
1. Fix Upgrade Problems
1. Upgrade Service Builder Services
1. Upgrade Customization Plugins


---

# Using Liferay Upgrade Planner

## Code Upgrade Tasks (cont.)

1. Upgrade Themes
1. Upgrade Layout Templates
1. Upgrade Frameworks & Features
1. Upgrade Portlets
1. Upgrade Web Plugins
1. Upgrade Ext Plugins 

---

# Using Liferay Upgrade Planner

## Upgrade Development Environment 

* Update workspace settings in `gradle.properties`
* Set `liferay.workspace.bundle.url` & `liferay.workspace.target.platform.version` to the version you intend to upgrade to
* Update `app.server.tomcat.version` (if necessary) 

---

# Using Liferay Upgrade Planner

## Migrate Plugins SDK Projects (Liferay 6.x)

* TODO

---

# Using Liferay Upgrade Planner

## Upgrade Build Dependencies

* Update Repository URL
* Update Workspace Plugin Version
* Remove Dependency Versions 

---

# Using Liferay Upgrade Planner

## Fix Upgrade Problems

* Auto-Correct Upgrade Problems
* Find Upgrade Problems
* Resolve Upgrade Problems
* Remove Problem Markers
* Resolving a Project's Dependencies
* Resolving Breaking Changes 

---

# Using Liferay Upgrade Planner

## Upgrade Service Builder Services

* TODO

---

# Using Liferay Upgrade Planner

## Upgrade Customization Plugins

* TODO


