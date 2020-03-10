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
1. .active[Liferay Workspace]
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
1. Export - Import
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

1. Gradle based project build

---

# Liferay Workspace

## Target Platform configuration

1. TODO

.footnote[
  See:

  https://github.com/liferay/liferay-portal/tree/master/modules/sdk/gradle-plugins-target-platform

  https://liferay.dev/blogs/-/blogs/what-is-the-target-platform-
]

---

# Liferay Workspace

## Tips and Tricks

1. TODO: How do I determine the versions of a particular target platform (e.g. which JUnit version is used)?


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
1. .active[Service- and Persistence-Layer]
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
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
  * TODO: How and when to configure Spring?
* Support for visual and wizard based modeling in Developer Studio

---

# Service Builder

## Features

* Object-Relational Mapping based on _Hibernate_
* Caching with _EHCache_


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

---

# Inspecting Generated Database Tables

## HSQL In Memory Database

1. Launch HSQL-GUI with:

  ```bash
  java -jar $LIFERAY_HOME/tomcat-9.0.17/lib/ext/hsql.jar
  ```

  > `$LIFERAY_HOME` must point to the base directory of your unpacked Liferay development bundle. The Tomcat version must match the development bundle's Tomcat version.

1. Connect to your database with the following settings:

  ```properties
  Recent Setting = <none> (default)
  Setting Name = <empty> (default)
  Type = HSQL Database Engine In-Memory (default)
  Driver = org.hsqldb.jdbcDriver
  URL = jdbc:hsqldb:file:LIFERAY_HOME/data/hypersonic/lportal
  User = SA (default)
  Password = <empty> (default)
  ```
---

# Service Implementation

## Development Steps

1. Define model in `service.xml`
1. Run `buildService` task of the respective module
1. Refresh the _liferay-workspace_ with `CTRL + F5`
1. Inspect the generated classes and interfaces in the _-api_ and _-service_ modules
1. Add or override _*LocalServiceImpl_, _*ServiceImpl_, and _*ModelImpl_ methods
1. Re-run `buildService` task in order to update the corresponding interfaces

---

# Service Implementation

## Naming Conventions

* _**fetch**Entity()_: TODO
* _**get**Entity()_: TODO


---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. .active[Testing]
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Testing]

.bottom-bar[
  {{title}}
]

---

# Implement a Test Module

## Auto-generate Persistence Tests

1. Configure `testDir` in `build.gradle` of the _-service_ module

  ```groovy
  buildService {
    apiDir = "../liferay-todo-list-api/src/main/java"
    testDir = "../liferay-todo-list-test/src/testIntegration/java"
  }
  ```
1. Run the `buildService` task (this will generate the required _-test_ module directory)
1. Configure the _-test_ module (`bnd.bnd` and `build.gradle`)
1. Run `testIntegration` task (to be found in the _verification_ node)
1. Inspect test results in _-test_ module `build/reports/tests/testIntegration/index.html`

.footnote[
  For dependencies configuration of `build.gradle` see: https://github.com/gamerson/liferay-workspace-test-dev/tree/master/modules/sample/sample-test
]

---

# Implement a Test Module

## Test Custom Methods

1. ...

---

# Implement a Test Module

## Mock Services and Objects

1. TODO: investigate `@Mock` annotation

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. .active[Presentation Layer]
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Presentation Layer]

.bottom-bar[
  {{title}}
]

---

# Presentation Layer

## Available Technologies

* JSP
* JSF
* React / Angular / Vue.js

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. .active[Permission Framework]
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Permission Framework]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. .active[Open API and REST]
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Open API and REST]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. .active[Asset Framework]
1. Search
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Asset Framework]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. .active[Search]
1. Managing User Associated Data (UAD)
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Search]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. .active[Managing User Associated Data (UAD)]
1. Workflows
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Managing User Associated Data (UAD)]

.bottom-bar[
  {{title}}
]

---

# Managing User Associated Data (UAD)

## GDPR Requirements

1. TODO
1. TODO

## UAD OOTB Features

1. TODO
1. TODO

## Enable Service Builder Custom Components

1. TODO
1. TODO

---

# Managing User Associated Data (UAD)

## Dependencies and Service Builder Configuration

* TODO

.footnote[
  See: https://help.liferay.com/hc/en-us/articles/360029848451-Adding-the-UAD-Framework-to-a-Service-Builder-Application
]

---

class: agenda

# .inner[Agenda]

.items[
1. Liferay Workspace
1. Service- and Persistence-Layer
1. Testing
1. Presentation Layer
1. Permission Framework
1. Open API and REST
1. Asset Framework
1. Search
1. Managing User Associated Data (UAD)
1. .active[Workflows]
1. Trash
1. Expando
]

---

title: Development with Liferay
layout: true

###.breadcrumbs[Development with Liferay › Workflows]

.bottom-bar[
  {{title}}
]
