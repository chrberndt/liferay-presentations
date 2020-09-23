title: Liferay Settings 
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
  Frankfurt am Main, 20 November 2020
]

---

class: agenda

# .inner[Agenda]

.items[
* .active[Introduction]
* Manual Settings Configuration 
* Portal Properties
* System Properties
* Environment Variables
* OSGi .config files
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › Introduction]

.bottom-bar[
  {{title}}
]

---

# Introduction

## Five Ways to Configure Liferay DXP 

1. Manual Settings Configuration 
1. Portal Properties
1. System Properties
1. Environment Variables
1. OSGi `.config` files

---

# Introduction

## Configuration Scopes 

* System Scope 
* Virtual Instance Scope 
* Site Scope
* Widget Scope 

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › Agenda]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Liferay Settings]

.items[
* Introduction
* .active[Manual Settings Configuration] 
* Portal Properties
* System Properties
* Environment Variables
* OSGi .config files
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › Manual Settings Configuration]

.bottom-bar[
  {{title}}
]

---

# Manual Settings Configuration

## Introduction

* TODO

---

class: agenda

# .inner[Liferay Settings]

.items[
* Introduction
* Manual Settings Configuration
* .active[Portal Properties]
* System Properties
* Environment Variables
* OSGi .config files
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › Portal Properties]

.bottom-bar[
  {{title}}
]

---

# Portal Properties

## Order of Precedence

* `portal.properties` located in `TODO.jar`
* `portal-ext.properties` located in `LIFERAY_HOME/portal-ext.properties`
* `portal-setup-wizard.properties` located in `LIFERAY_HOME/portal-setup-wizard.properties`
* Settings persisted to the database

## Current Value

* Can be obtained from *Control Panel → Server Administration → Properties → Portal Properties*

---

# Portal Properties

## Propagation in the Cluster 

* TODO

---

class: agenda

# .inner[Liferay Settings]

.items[
* Introduction
* Manual Settings Configuration
* Portal Properties
* .active[System Properties]
* Environment Variables
* OSGi .config files
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › System Properties]

.bottom-bar[
  {{title}}
]

---

# System Properties

## Default Configuration

* TODO

## Current Value

* Can be obtained from *Control Panel → Server Administration → Properties → System Properties*

---

# System Properties

## Propagation in the Cluster 

* TODO

---

class: agenda

# .inner[Liferay Settings]

.items[
* Introduction
* Manual Settings Configuration
* Portal Properties
* System Properties
* .active[Environment Variables]
* OSGi .config files
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › Environment Variables]

.bottom-bar[
  {{title}}
]

---

# Environment Variables 

## Introduction

* TODO

---

class: agenda

# .inner[Liferay Settings]

.items[
* Introduction
* Manual Settings Configuration
* Portal Properties
* System Properties
* Environment Variables
* .active[OSGi .config Files]
]

---

title: Liferay Settings 
layout: true

###.breadcrumbs[Liferay Settings › OSGi .config files]

.bottom-bar[
  {{title}}
]

---

# OSGi `.config` Files

## Introduction

* Named after the corresponding configuration interface, e.g. `com.liferay.blogs.configuration.BlogsConfiguration.config`
* Use value format defined by the Apache Felix Configuration Admin framework. 
* Stored in `$LIFERAY_HOME/osgi/configs`
* TODO: typed
* TODO: changes automatically propagated to all cluster nodes?

.footnote[
  https://learn.liferay.com/dxp/7.x/en/system-administration/system-settings/using-configuration-files.html

  https://github.com/apache/felix-dev/tree/master/configadmin 
]

---

# OSGi `.config` Files

## Using `.config` Files

* Reset to default values: TODO
* Export current settings: TODO
* Deploy settings: TODO

---

class: agenda

# .inner[Thank You!]

.items[
* .active[christian.berndt@liferay.com]
* .active[linkedin.com/in/mr-christian-berndt]
]
