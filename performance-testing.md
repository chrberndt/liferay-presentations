title: Performance Testing
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---
class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Performance Testing

# {{title}}

christian.berndt@liferay.com

.date[
  Vienna, 20 November 2022
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Overview]
]

---

title: Performance Testing
layout: true

###.breadcrumbs[Performance Testing › Overview]

.bottom-bar[
  {{title}}
]

---

# Performance Testing

## Introduction

* Load Testing: verify that a server can handle a given number requests / users / queries / etc.
* Stress Testing: determine the maximum number of requests / users / etc. a server can handle

---

# Performance Testing

## Subtasks

* Load Testing
* Stress Testing

---

# Performance Testing

## Prerequisities

* Define the number of requests a server is supposed to handle (within a given period)
* Determine relevant usage peaks
* Determine relevant usage patterns / page flows, e.g.
  * Transaction centric scenarios (Online banking, flight booking etc.)
  * Collaboration centric scenarios (Intranet)

---

# Load Testing

## A Load Testing Example

* 1 million total users.
* 2 million documents with an average of 100KB per document.
* 10,000 sites with 50% of the sites having at least 5 children.
* 4 million message forum threads and posts.
* 100,000 blog entries and 1 million comments.
* 100,000 wiki pages.

.footnote[
  From Liferay DXP Performance Benchmark Study of Liferay DXP 7.3, p. 1.
]

---

class: agenda

# .inner[Performance Testing]

.items[
1. Overview
1. .active[Load Testing]
1. Pagespeed
]

---

title: Performance Testing
layout: true

###.breadcrumbs[Performance Testing › Load Testing]

.bottom-bar[
  {{title}}
]

---

# Load Testing

## Overview

* Tooling

---

# Tooling

* JMeter
* Glowroot
* Grinder

.footnote[
]

---

# JMeter

## Basic Setup on localhost

1. Download latest JMeter from [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)
1. Extract and run GUI with `./JMETER_HOME/bin/jmeter`
1. Create a new *Test Plan* based on the *Recording* Template

  File → Templates → Recording

1. Fill in your parameters:

  hostToRecord: *localhost*</br>
  recordingOutputFile: *recording.xml* (default)</br>
  schemeToRecord: http

---

class: agenda

# .inner[Performance Testing]

.items[
1. Overview
1. Load Testing
1. .active[Pagespeed]
]

title: Performance Testing
layout: true

###.breadcrumbs[Performance Testing › Pagespeed]

.bottom-bar[
  {{title}}
]

---

# Pagespeed

## Overview

* Tools

---

# Tools

* https://developers.google.com/speed/pagespeed/insights
* https://www.webpagetest.org/

