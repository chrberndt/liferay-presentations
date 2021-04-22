title: Adding Trash Helper Support 
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

###.breadcrumbs[Trash Helper › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms

TODO

.footnote[
https://help.liferay.com/hc/en-us/articles/360018179491-Introduction-to-Recycle-Bin
]

---

class: agenda

# .inner[Adding Trash Helper Support]

.items[
1. Concepts and Terms
1. .active[Implementation Steps]
]

---

title: Implementation Steps 
layout: true

###.breadcrumbs[Trash Helper › Implementation Steps]

.bottom-bar[
  {{title}}
]

---

# Implementation Steps

## Overview

1. Enable Trash in service.xml 
1. Create service methods
1. Implement a Trash Handler for each trash enabled entity
1. Handle trash in search related methods
1. Create front-end controls
1. Implement a Trash Renderer for each trash enabled entity 

.footnote[
]

---

# Implementation Steps

## Enable Trash in service.xml 

```
<entity local-service="true" name="Task" remote-service="true" uuid="true" trash-enabled="true">
```
---

# Implementation Steps

## Create service methods
 
### Add trash handling methods to local service

* `move<Entities>ToTrash(long groupId, long userId)`
* `move<Entity>ToTrash(long userId, <Entity> entity)`
* `move<Entity>ToTrash(long groupId, long <entity>Id)`
* `restore<Entity>FromTrash(long userId, long <entity>Id)`

### Add trash handling methods to remote service

* `move<Entity>ToTrash(long <entity>Id)`
* `restore<Entity>FromTrash(long <entity>Id)` 

---

# Implementation Steps

## Implement a Trash Handler for each trash enabled entity

* <Entity>TrashHandler.java

---

# Implementation Steps

## Handle trash in search related methods

* TODO

---

# Implementation Steps

## Create trash aware front-end controls

* <Entity>ManagementToolbarDisplayContext
* ActionUtil
* Edit<Entity>MVCActionCommand
