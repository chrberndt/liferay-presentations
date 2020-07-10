title: CI/CD with Liferay
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
1. Tools 
]

---

title: Concepts and Terms 
layout: true

###.breadcrumbs[CI/CD › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms 

## Overview

* DevOps 

---

class: agenda

# .inner[CI/CD with Liferay]

.items[
1. Concepts and Terms 
1. .active[Tools]
]

---

title: Tools 
layout: true

###.breadcrumbs[CI/CD › Tools]

.bottom-bar[
  {{title}}
]

---

# Tools 

## Overview

* Jenkins 

---

# Jenkins

## Introduction 

* Open source automation server
* Used to *build*, *test*, *deliver*, and *deploy* software  

---

# Jenkins

## Concepts and Terms

* Jenkins Pipeline
* Jenkinsfile
* Plugins
* Handling Credentials
* Deployments

---

# Jenkins

## Jenkins Pipeline

* A suite of plugins which supports implementing and integrating *continuous delivery pipelines*
* Typically written into a text file called `Jenkinsfile`

.footnote[
  https://www.jenkins.io/doc/pipeline/tour/hello-world/
]

---

# Jenkins

## Jenkinsfile: An Example

```Jenkinsfile
pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}
```

.footnote[
Source: https://www.jenkins.io/doc/pipeline/tour/deployment/
]

---

# Jenkins

## Jenkinsfile: Sections

* `agent`: Tells Jenkins where and how to execute the Pipeline
* `stages`: TODO
* `stage`: TODO
* `steps`
* `post`: TODO (valid sections, e.g. `always`, `success`, `failure`, `changed`)

---

# Jenkins

## Jenkinsfile: The `agent` Section

* Tells Jenkins where and how to execute the Pipeline, or subset thereof.
* Required for all Pipelines.
* Default types: `[any, label, none]`
* Provided by Plugins: `docker` (requires *Docker* and *Docker Pipeline* plugins to be installed)

.footnote[
https://www.jenkins.io/doc/pipeline/tour/agents/
]

---

# Jenkins

## Jenkinsfile: The `steps` Section

> Think of a "step" like a single command which performs a single action. When a step succeeds it moves onto the next step. When a step fails to execute correctly the Pipeline will fail.

* On Linux, BSD, and Mac OS (Unix-like) systems, the `sh` step is used to execute a shell command in a Pipeline.
* Windows-based systems should use the `bat` step for executing batch commands.
* May include wrapper steps like `retry` and `timeout`

.footnote[
https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/
]

---

# Jenkins

## Jenkinsfile: The `post` Section

* Used to run clean-up steps or perform actions based on the outcome of the Pipeline.

.footnote[
https://www.jenkins.io/doc/pipeline/tour/running-multiple-steps/
]

---

# Jenkins

## Jenkinsfile: Environment Variables

* TODO

.footnote[
https://www.jenkins.io/doc/pipeline/tour/environment/
]

---

# Jenkins

## Plugins Installation

* Jenkins → Manage Jenkins → System Configuration → Manage Plugins

---

# Jenkins

## Handling Credentials

* TODO

.footnote[
https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#handling-credentials
]

---

# Jenkins

## Deployments

* TODO

.footnote[
https://www.jenkins.io/doc/pipeline/tour/deployment/
]
