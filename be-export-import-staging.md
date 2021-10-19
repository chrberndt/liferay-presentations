title: Export, Import, Staging 
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

###.breadcrumbs[Export, Import, Staging › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms

TODO

.footnote[
[https://help.liferay.com/hc/en-us/articles/360018167951-Introduction-to-Export-Import-and-Staging (7.1)](https://help.liferay.com/hc/en-us/articles/360018167951-Introduction-to-Export-Import-and-Staging)
]

---

class: agenda

# .inner[Export, Import, Staging]

.items[
1. Concepts and Terms
1. .active[Implementation Steps]
]

---

title: Implementation Steps 
layout: true

###.breadcrumbs[Export, Import, Staging › Implementation Steps]

.bottom-bar[
  {{title}}
]

---

# Implementation Steps

## Overview

1. Add column `lastPublishDate` in service.xml (required for staging)
1. Immplement Data Handlers

.footnote[
]

---

# Implementation Steps

## Add column `lastPublishDate` in service.xml

```
		<!-- Staging -->
		
		<column name="lastPublishDate" type="Date" />
```

Rerun of `buildService` task will add `StagedGroupedModel` interface to your entity's model class.

.footnote[
https://help.liferay.com/hc/en-us/articles/360018167991-Generating-Staged-Models-Using-Service-Builder-
]

---

# Implementation Steps

## Implement Data Handlers

.footnote[
]
