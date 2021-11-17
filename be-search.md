title: Integrating With Search 
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
1. Development Setup
1. Implementation Steps
]

---

title: Concepts and Terms 
layout: true

###.breadcrumbs[Integrating With Search › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms 

* Search Engine
* Inverted Index
* Indexing
* Querying 

---

class: agenda

# .inner[Integrating With Search]

.items[
1. Concepts and Terms
1. .active[Development Setup]
1. Implementation Steps
]

---

title: Development Setup 
layout: true

###.breadcrumbs[Integrating With Search › Development Setup]

.bottom-bar[
  {{title}}
]

---

# Development Setup 

## Overview

1. Elasticsearch (see: liferay-docker-examples/liferay-stack) 
1. Kibana (see: liferay-docker-examples/liferay-stack) 

.footnote[
]

---

# Elasticsearch

## Setup

1. Elasticsearch (see: liferay-docker-examples/liferay-stack) 

---

# Elasticsearch

## Explore ES

```bash
# Check your connection to ES
curl -X GET localhost:9200

# Query your index
curl -X GET localhost:9200/_search
```
---

# Kibana

## Setup 

1. Kibana (see: liferay-docker-examples/liferay-stack)

## Connection

1. http://127.0.0.1:5601

---

class: agenda

# .inner[Integrating With Search]

.items[
1. Concepts and Terms
1. Development Setup
1. .active[Implementation Steps]
]

---

title: Implementation Steps 
layout: true

###.breadcrumbs[Integrating With Search › Implementation Steps]

.bottom-bar[
  {{title}}
]

---

# Implementation Steps

## Overview

1. ModelDocumentContributor


.footnote[
]

---

# ModelDocumentContributor 

1. TODO

