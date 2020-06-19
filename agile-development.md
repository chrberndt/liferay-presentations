title: Agile Development with Liferay 
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
* .active[Terms and Concepts]
* Testing Methodology 
* Tools and Frameworks
* Configure Liferay Integration Tests
* Setup a Continous Integration Pipeline
* Setup a Continous Delivery Pipeline
]

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Terms and Concepts]

.bottom-bar[
  {{title}}
]

---

# Terms and Concepts 

* Agile Development
* Scrum, Kanban, ...
* DevOps

---

# Agile Development: History

* ...

---

# Agile Development

## Key Concepts

* Adaptive planning
* Evolutionary development
* Early delivery
* Continual improvement

---

# Scrum: Introduction

## An agile process framework designed for teams of ten or fewer members

* Sutherland / Schwaber 1995 (based on older research)
* Schwaber and Beedle, _Agile Software Development with Scrum_, 2001
* 2002: Scrum Alliance (Schwaber): _Certified Scrum_
* 2009: scrum.org: _Professional Scrum_
* 2009: _The Scrum Guide_ (latest revision November 2017)

Source: https://en.wikipedia.org/wiki/Scrum_(software_development) 

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Agenda]

.bottom-bar[
  {{title}}
]

---

class: agenda

# .inner[Agile Development with Liferay]

.items[
* Terms and Concepts
* .active[Testing Methodology] 
* Tools and Frameworks
* Configure Liferay Integration Tests
* Setup a Continous Integration Pipeline
* Setup a Continous Delivery Pipeline
]

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Testing Methodology]

.bottom-bar[
  {{title}}
]

---

# Testing Methodology

## Introduction

* Testing is an essential phase of any development methodology / project.

---

# Testing Methodology

## Test Driven Development (TDD)

* Frequently used in both extreme programming (XP) and Scrum
* Unit tests are created before the code itself is written
* When the tests pass, that code is considered complete

Source: https://en.wikipedia.org/wiki/Unit_testing

---

# Testing Methodology 

## Types of Tests

* Unit Tests
* Integration Tests
* Acceptance Tests
* Smoke Tests
* Regression Tests

---

# Unit Tests

## Objective

* Ensure that a section of an application (the "unit") meets its design and behaves as intended

## Advantages

* Find problems early in the development cycle
* Facilitate refactoring and upgrades

.footnote[
  Source: https://en.wikipedia.org/wiki/Unit_testing
]

---

# Unit Tests

## Example

---

class: agenda

# .inner[Agile Development with Liferay]

.items[
* Terms and Concepts
* Testing Methodology 
* .active[Tools and Frameworks]
* Configure Liferay Integration Tests
* Setup a Continous Integration Pipeline
* Setup a Continous Delivery Pipeline
]

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Tools and Frameworks]

.bottom-bar[
  {{title}}
]

---

# Tools and Frameworks

* JUnit
* Arquillian
* Jest

---

# JUnit

* TODO

---

# Arquillian

* TODO

---

# Jest

* Javascript Testing Framework

.footnote[
  https://jestjs.io
]
---

# Jest

## Using Jest with Liferay React Components

* Resources: https://liferay.slack.com/archives/C03CAD9EF/p1590163518113600

---

# Poshi Tests

* Resources: https://loop.liferay.com/es/home/-/loop/feed/21246922

---

class: agenda

# .inner[Agile Development with Liferay]

.items[
* Terms and Concepts
* Testing Methodology
* Tools and Frameworks
* .active[Configure Liferay Integration Tests]
* Setup a Continous Integration Pipeline
* Setup a Continous Delivery Pipeline
]

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Configure Liferay Integration Tests]

.bottom-bar[
  {{title}}
]

---

# Configure Liferay Integration Tests

## Overview

* Create a Test Module
* Configure Test Dependencies
* Determine Test Dependency Versions 

---

# Configure Liferay Integration Tests

## Create a Test Module

1. ...
1. Add `testDir` property to `build.gradle` in *-service* module (optional)

```groovy
buildService {
  apiDir = "../liferay-todo-list-api/src/main/java"
  testDir = "../liferay-todo-list-test/src/testIntegration/java"
}
```

---

# Configure Liferay Integration Tests

## Configure Test Dependencies

```groovy
dependencies {
  // template start
  testCompile group: "com.liferay", name: "com.liferay.petra.lang"
  testCompile group: "com.liferay", name: "com.liferay.petra.string"
  testCompile group: "com.liferay", name: "com.liferay.registry.api"
  testCompile group: "com.liferay.portal", name: "com.liferay.portal.kernel"
  testCompile group: "javax.portlet", name: "portlet-api"
  testCompile group: "junit", name: "junit"
  testCompile group: "org.apache.felix", name: "org.apache.felix.http.servlet-api", version: "1.1.2"
  testCompile group: "org.osgi", name: "org.osgi.core"
  testCompile group: "org.springframework", name: "spring-test"
  testCompile group: "org.slf4j", name: "slf4j-api"

  testIntegrationCompile group: "com.liferay", name: "com.liferay.arquillian.extension.junit.bridge", version: "1.0.19"
  testIntegrationCompile group: "com.liferay.portal", name: "com.liferay.portal.test", version: "6.0.7"
  testIntegrationCompile group: "com.liferay.portal", name: "com.liferay.portal.test.integration", version: "6.0.7"
  testIntegrationCompile group: "log4j", name: "log4j", version: "1.2.17"
  // template end

  // service builder template start
  testIntegrationCompile project(":modules:sample:sample-api")
  testIntegrationCompile project(":modules:sample:sample-service")
  // service builder template end

  // these will be fixed by workspace
  testModules group: "com.liferay", name: "com.liferay.arquillian.extension.junit.bridge.connector", version: "1.0.0"
  testModules group: "com.liferay.portal", name: "com.liferay.portal.test", version: "6.0.7"
  testModules group: "com.liferay.portal", name: "com.liferay.portal.test.integration", version: "6.0.7"
  testModules group: "org.apache.aries.jmx", name: "org.apache.aries.jmx.core", version: "1.1.7"

  // this will no longer be necessary once we fix DestinationSyncRule
  testModules group: "com.liferay", name: "com.liferay.sync.api", version: "5.0.6"
  testModules group: "com.liferay", name: "com.liferay.sync.service", version: "3.0.9"
}

// the following configurations will no longer be necessary in future versions of workspace
copyTestModules {
  dependsOn ":modules:sample:sample-api:deploy", ":modules:sample:sample-service:deploy"
}

setUpTestableTomcat {
  dependsOn ":initBundle"
}
```

.footnote[
https://github.com/gamerson/liferay-workspace-test-dev/blob/master/modules/sample/sample-test/build.gradle
]

---

# Configure Liferay Integration Tests

## Determine Test Dependency Versions

* Check `portal-test.properties` and `portal-test-integration.properties`
* e.g. https://github.com/liferay/liferay-portal/blob/7.2.1-ga2/modules/.releng/portal-test.properties  
* e.g. https://github.com/liferay/liferay-portal/blob/7.2.1-ga2/modules/.releng/portal-test-integration.properties  

---

class: agenda

# .inner[Agile Development with Liferay]

.items[
* Terms and Concepts
* Testing Methodology
* Tools and Frameworks
* Configure Liferay Integration Tests
* .active[Setup a Continous Integration Pipeline]
* Setup a Continous Delivery Pipeline
]

---

title: Agile Development with Liferay
layout: true

###.breadcrumbs[Agile Development with Liferay › Setup a Continous Integration Pipeline]

.bottom-bar[
  {{title}}
]

---

# Setup a Continous Integration Pipeline

* ...

---

class: agenda

# .inner[Agile Development with Liferay]

.items[
* Terms and Concepts
* Testing Methodology
* Tools and Frameworks
* Configure Liferay Integration Tests
* Setup a Continous Integration Pipeline
* .active[Setup a Continous Delivery Pipeline]
]

---

title: Agile Development with Liferay 
layout: true

###.breadcrumbs[Agile Development with Liferay › Setup a Continous Delivery Pipeline]

.bottom-bar[
  {{title}}
]

---

# Setup a Continous Delivery Pipeline

* ...
  
---

class: agenda

# .inner[Thank You!]

.items[
* christian.berndt@liferay.com
* linkedin.com/in/mr-christian-berndt
]
