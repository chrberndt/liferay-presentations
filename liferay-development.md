title: Development with Liferay 
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
1. .active[Service- and Persistence-Layer]
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
]

---

title: Development with Liferay 
layout: true

###.breadcrumbs[Development with Liferay › Service- and Persistence Layer]

.bottom-bar[
  {{title}}
]

---

# Service Builder

## Introduction

* Liferay's code generation tool
* Dependency injection either via _OSGI Declarative Services_ (default) or _Spring_
  * How and when to configure Spring? 
* Support for visual and wizard based modeling in Developer Studio

---

# service.xml

## `<service-builder>` Attributes and Configuration Sections 

`<author>` the user name associated with the generated classes

`<namespace>` unique namespace for a component (prepended to database table names)

`<entity>` one or more entities that constitute the model

`<exceptions>` custom exceptions thrown by a component

`<service-builder-import>` split the Service Builder configuration into multiple files

.footnote[
  Source: http://www.liferay.com/dtd/liferay-service-builder_7_2_0.dtd
]

---

# service.xml

## `<entity>` Attributes (selected)

`name` specifies the name of the entity

`local-service` if true, then the service will generate the local interfaces for the service (default: false) 

`remote-service` if true, then the service will generate remote interfaces for the service (default: false)

`trash-enabled` whether trash related methods should be generated or not 

`uad-application-name` the name of the application that the entity type belongs to in the GDPR UI 

`uad-auto-delete` whether the entity should be automatically deleted during auto-anonymization 

`versioned` if true, the service will generate a version table, columns, and methods to version the entity


.footnote[
  Source: http://www.liferay.com/dtd/liferay-service-builder_7_2_0.dtd
]

---

# service.xml

## `<entity>` Configuration Sections 

`<column>` TODO

`<order>` TODO

`<finder>` TODO

`<reference>` TODO

`<localized-entity>` TODO

.footnote[
  Source: http://www.liferay.com/dtd/liferay-service-builder_7_2_0.dtd
]
