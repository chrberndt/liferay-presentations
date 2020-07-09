title: Content Management with Liferay
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
1. .active[Concepts and Terms]
1. Content Sets
1. Staging 
]

---

title: Concepts and Terms 
layout: true

###.breadcrumbs[Content Management › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms 

.col-4[
## User Management 

* User
* User Group
* Organization
]

.col-4[
## Content Management
* Site
* Page (Layout)
* Content Pages, Fragments, Resources, and Collections
* Widget Pages and Widgets
]

.col-4[
]

---

# Concepts and Terms

## User

* Every person who accesses a Liferay site
* Unauthenticated users are called *Guest* user

.footnote[
https://learn.liferay.com/dxp/7.x/en/users-and-permissions/users/understanding-users.html
]

---

# Concepts and Terms

## User Group

* A non-hierarchical way to group users
* Maps automatically to LDAP Groups
* May have a User Group Site

---

# Concepts and Terms

## Organization

* A hierarchical way to group users
* May have an Organization Site

---

# Concepts and Terms

## Site: General Characteristics

* A container for content and pages
* May have both public and private sections
* May be stacked hierarchically

---

# Concepts and Terms

## Site: Hierarchies

* Child sites inherit *Structures* and *Templates* from their parent sites
* Child sites inherit *Vocabularies* and *Categories* from their parent sites
 
---

# Concepts and Terms

## Page (Layout)

* 

---

# Concepts and Terms

## Content Pages, Fragments, Resources, and Collections


* Fragment Collections are shared between different sites via *Global* scope (DXP 7.2 SP1+)

.footnote[
https://help.liferay.com/hc/en-us/articles/360032884532-Creating-Page-Fragments
]

---

class: agenda

# .inner[Content Management with Liferay]

.items[
1. Concepts and Terms 
1. .active[Content Sets]
1. Staging
]

---

title: Content Sets 
layout: true

###.breadcrumbs[Content Management › Content Sets]

.bottom-bar[
  {{title}}
]

---

# Content Sets

## Overview

*  

.footnote[
  https://help.liferay.com/hc/en-us/articles/360029133311-Creating-Content-Sets
]

---

# Content Sets

## Creating a Content Set

1. Site Administration → Content & Data → Content Sets

---

# Content Sets

## Content Set Personalization

.footnote[
  https://help.liferay.com/hc/en-us/articles/360029041771-Content-Set-Personalization
]

---

class: agenda

# .inner[Content Management with Liferay]

.items[
1. Concepts and Terms 
1. Content Sets
1. .active[Staging]
]

---

title: Staging 
layout: true

###.breadcrumbs[Content Management › Staging]

.bottom-bar[
  {{title}}
]

---

# Staging 

## Overview

* TODO

---

# Staging

## Example Use Cases

* Recompose a page / site in a space inaccessible to the general public
* Schedule page / site / content modifications for a later date
* Collaborate with multiple teams on page / site / content modifications
