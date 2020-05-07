title: Tuning Liferay 
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
* .active[Tuning the Liferay Platform] 
* Tuning the Database
* Tuning the Search-Engine
* Tuning the Operating System
]

---

title: Tuning Liferay 
layout: true

###.breadcrumbs[Tuning Liferay › Tuning the Liferay Application]

.bottom-bar[
  {{title}}
]

---

# Tuning the Liferay Application

## Resources

* https://www.liferay.com/resource?folderId=3292406&title=Liferay+DXP+7.2+Deployment+Checklist

---

# Tuning the Liferay Application

## JVM Monitoring Tools

* JConsole
* JVisualVM
* Glowroot
* JCEasy (Garbage Collector Monitoring)

---

# Tuning the Liferay Application

## Analyzing Memory Consumption

1. Create heap dump with `jmap -dump:[live],format=b,file=<file-path-to-store-dump> <java_process_id>`
1. Analyze dump with Eclipse Memory Analyzer Tool (MAT) (https://www.eclipse.org/mat)

---

class: agenda

# .inner[Thank You!]

.items[
* christian.berndt@liferay.com
* linkedin.com/in/mr-christian-berndt
]
