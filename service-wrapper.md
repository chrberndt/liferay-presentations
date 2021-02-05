title: Service Wrapper 
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
  Frankfurt am Main, 20 November 2021
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Introduction]
1. Implementing a Service Wrapper 
]

---

title: Introduction 
layout: true

###.breadcrumbs[Service Wrapper › Introduction]

.bottom-bar[
  {{title}}
]

---

# Introduction 

* Extension Point for customizing or extending Liferay Service Builder services 

---

class: agenda

# .inner[Service Wrapper]

.items[
1. Introduction
1. .active[Implementing a Service Wrapper]
]

---

title: Implementing a Service Wrapper 
layout: true

###.breadcrumbs[Service Wrapper › Implementing a Service Wrapper]

.bottom-bar[
  {{title}}
]

---

# Implementing a Service Wrapper

## Implementation Steps

1. Determine the Service Builder Service class to override, e.g. `LayoutLocalService`
1. Create a Liferay module project based on the service-wrapper template



.footnote[
  https://help.liferay.com/hc/en-us/articles/360029144671-Overriding-Liferay-Services-Service-Wrappers-
]

---

# Implementing a Service Wrapper

## Creating a Liferay module project based on the service-wrapper template

```bash
blade create -t service-wrapper -p com.chberndt.liferay.service.wrapper -c LayoutServiceOverride -s LayoutLocalServcie my-service-wrapper
```


