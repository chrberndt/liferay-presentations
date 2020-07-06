title: CI / CD with Liferay 
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
1. .active[Concepts and Terms]
1. Tools 
]

---

title: Concepts and Terms 
layout: true

###.breadcrumbs[CI / CD › Concepts and Terms]

.bottom-bar[
  {{title}}
]

---

# Concepts and Terms 

## Overview

* DevOps 

---

class: agenda

# .inner[CI / CD]

.items[
1. Concepts and Terms 
1. .active[Tools]
]

---

title: Tools 
layout: true

###.breadcrumbs[CI / CD › Tools]

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
    stages {
        stage('Test') {
            steps {
               //  sh 'echo "Fail!"; exit 1'
               sh 'echo "Success!"; exit 0'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
```
---

# Jenkins

## Jenkinsfile: Sections

* `agent`: TODO (valid values, prerequisites)
* `stages`: TODO
* `stage`: TODO
* `steps`
* `post`: TODO (valid sections, e.g. `always`, `success`, `failure`, `changed`)

---

# Jenkins

## The `agent` Section

* The `agent` directive tells Jenkins where and how to execute the Pipeline, or subset thereof.
* Required for all Pipelines.

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


