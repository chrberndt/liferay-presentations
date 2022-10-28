title: Client Side Frameworks 
class: animation-fade
layout: true

.bottom-bar[
  {{title}}
]

---
class: impact

.logo[<img src="images/liferay-waffle.svg">]

## Client Side Frameworks 

# {{title}}

christian.berndt@liferay.com

.date[
  Vienna, 20 November 2021
]

---

class: agenda

# .inner[Agenda]

.items[
1. .active[Overview]
1. React 
1. Angular
1. VueJS
]

---

title: Client Side Frameworks 
layout: true

###.breadcrumbs[Client Side Frameworks › Overview]

.bottom-bar[
  {{title}}
]

---

# Client Side JS Frameworks

## Introduction

* Adapt scripts available for all major frameworks (REACT, Angular, Vue.js)
* ...

---

# Client Side JS Frameworks

## Challenges

* Limited Control of the DOM
* Client-Side Routing
* Interoperation with Liferay JS
* Coexistence with other frameworks on the page (Senna, jQuery, ...)
* Multiple React/Angular/Vue applications on one page
* Multiple instances of the same app on one page

---

# Client Side JS Frameworks

## Examples Provided by Liferay

* https://liferay.github.io/liferay-frontend-projects/

---

class: agenda

# .inner[Client Side Frameworks]

.items[
1. Overview
1. .active[React] 
1. Angular
1. VueJS
]

---

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › React]

.bottom-bar[
  {{title}}
]

---

# React 

## Overview

* Tooling
* Creating a Liferay React Widget Module
* Embedding a React Component in JSP
* Using Clay Components

---

# Tooling

* `yarn` - make sure to use `yarn` to manage your npm dependencies, see: [https://liferay.dev/blogs/-/blogs/liferay-gradle-yarn-workspaces](https://liferay.dev/blogs/-/blogs/liferay-gradle-yarn-workspaces)
* `deployFast` (see: https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task)

.footnote[
  [https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task](https://github.com/liferay/liferay-frontend-projects/blob/master/guidelines/dxp/environment.md#enabling-the-deployfast-task)
]

---

# Creating a Liferay React Widget Module

1. Create a React app with `create-react-app`

  ```bash
  npx create-react-app my-app
  ```
1. Adapt the React app to Liferay with `yo liferay-js:adapt`

  ```bash
  yo liferay-js:adapt
  ```

.footnote[
1. [https://create-react-app.dev](https://create-react-app.dev)
1. [https://github.com/liferay/liferay-frontend-projects/blob/master/maintenance/projects/js-toolkit/docs/How-to-adapt-most-popular-frameworks-projects.md](https://github.com/liferay/liferay-frontend-projects/blob/master/maintenance/projects/js-toolkit/docs/How-to-adapt-most-popular-frameworks-projects.md)
]

---

# Example: Retrieve a List of Blog Posts

* See: [https://github.com/lgdd/lfug20-react-workshop#lfug-20-meetup--react-workshop](https://github.com/lgdd/lfug20-react-workshop#lfug-20-meetup--react-workshop)

---

# Embedding a React Component in JSP

## Intrdocution

* A common paradigm in Liferay frontend development
* Useful, for example, to customize default components

---

# Embedding a React Component in JSP

## Implementation Steps

1. Create a Liferay Module Project of type `mvc-portlet`
1. Configure `Web-ContextPath` in `bnd.bnd`
1. Include resources created by `packageRunBuild` into module (`bnd.bnd`)
1. Configure JS dependencies in `package.json` (name attribute must match Web-ContextPath in `bnd.bnd`)
1. Implement React Component
1. Use `<react:component />` tag to render the component within your JSP

---

# Using Clay Components

## Introduction

* Clay: a set of React based components created and maintained by Liferay
* Usable in custom React components embedded in JSP
* TODO: usable in standalone widgets based on React?

---

class: agenda

# .inner[Client Side Frameworkst]

.items[
1. Overview
1. React
1. .active[Angular]
1. VueJS
]

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › Angular]

.bottom-bar[
  {{title}}
]

---

# Angular 

## Overview

* TODO

---

class: agenda

# .inner[Client Side Frameworks]

.items[
1. Overview
1. React
1. Angular
1. .active[VueJS]
]

---

title: Client Side Frameworks
layout: true

###.breadcrumbs[Client Side Frameworks › VueJS]

.bottom-bar[
  {{title}}
]

---

# VueJS 

## Overview

* Set Up Vue Environment
* Create Liferay Workspace
* Configure Liferay Workspace
* Create and Deploy a VueJS Widget
* Refactor VueJS Widget to Use Webpack and Common VueJS Tooling I
* Refactor VueJS Widget to Use Webpack and Common VueJS Tooling II


---

# Set Up Vue Environment

1. Set up Node (16.18.0 at the time of time of writing (October 2022))

    `nvm install lts` (on Windows)

    `n install lts` (on Linux)

1. Set up latest version of Vue.js (3.2.28 at the time of writing (October 2022))

    `npm init vue@latest` (will install create-vue (@3.3.4 at the time of writing))

1. Create you first project, install project dependencies, launch the development server and start developing

    ```
    vue create my-first-vue-app
    cd my-first-vue-app
    npm install
    npm run serve
    ```
---

# Create Liferay Workspace

1. Install `blade`

    `curl -L https://raw.githubusercontent.com/liferay/liferay-blade-cli/master/cli/installers/local | sh`

1. Create a Liferay workspace

    `blade init my-liferay-workspace` and choose your target platform version or the latest release (portal-7.4-ga46 at the time of writing (October 2022))

.footnote[
  [https://learn.liferay.com/dxp/latest/en/building-applications/tooling/blade-cli/installing-and-updating-blade-cli.html](https://learn.liferay.com/dxp/latest/en/building-applications/tooling/blade-cli/installing-and-updating-blade-cli.html)
]
---

# Configure Liferay Workspace

1. Configure a current node version for the workspace

    In `build.gradle` at the root of the workspace add:

    ```
    allprojects {
	    plugins.withId("com.liferay.node") {
		    node.global = true
		    node.nodeVersion = '12.21.0'
		    node.npmVersion = '6.14.11'
	    }
    }
    ```

1. Download and start Liferay development server

    `cd my-liferay-workspace`

    `./gradlew initBundle`

    `./bundles/tomcat-9.0.65/bin/catalina.sh run`

.footnote[
  [https://rotty3000.doublebite.com/javascript-build-in-liferay-workspace-module](https://rotty3000.doublebite.com/javascript-build-in-liferay-workspace-module)
]
---

# Create And Deploy a VueJS Widget

1. Create a VueJS Widget

    `blade create -t npm-vuejs-portlet my-npm-vuejs-portlet`

1. Build and deploy

    `./gradlew deploy`

---

# Refactor VueJS Widget to Use Webpack and Common VueJS Tooling I

1. Upgrade to latest version of VueJS (3.2.13 at the time of writing (October 2022))

    in `package.json`: `"vue": "^3.2.13"`

1. Add default dependencies of a common VueJS project

    `npm install core-js --save`

1. Add minimal development dependencies of a VueJS project using Typescript

    ```
    npm install @vue/cli-plugin-typescript --save-dev
    npm install typescript --save-dev
    ```

---

# Refactor VueJS Widget to Use Webpack and Common VueJS Tooling II

1. Configure Typescript settings via `tsconfig.json`

    Use the Typescript configuration of a vanilla VueJS project with Typescript support as starting point:

    `cp ~/my-first-vue-app-with-typescript/tsconfig.json ~/my-liferay-workspace/modules/my-npm-vuejs-portlet/`

1. Use vuejs-service

    `npm install @vue/cli-service --save-dev`

1. Build JS with vuejs-service

    in `package.json`:

    `"build": "vue-cli-service build"`

---

# Refactor VueJS Widget to Use Webpack and Common VueJS Tooling III

1. Remove obsolete devDependencies from `package.json`

    `babel-cli`, `babel-preset-env`, `liferay-npm-bundler`

1. Align JS-directory name with Vue convention

    `mv modules/my-npm-vuejs-portlet/src/main/resources/META-INF/resources/lib modules/my-npm-vuejs-portlet/src/main/resources/META-INF/resources/js`

---

# Refactor VueJS Widget to Use Webpack and Common VueJS Tooling IV

1. Configure @vue/cli-service to operate within the OSGi module layout (via `vue.config.js`)

    ```javascript
    const path = require("path");

    module.exports = {
      chainWebpack: config => {
        config
          .entry("app")
          .clear()
          .add("./src/main/resources/META-INF/resources/js/main.ts")
          .end();
        config.resolve.alias
          .set("@", path.join(__dirname, "./src/main/resources/META-INF/resources/js"))
      },
      filenameHashing: false,
      outputDir: "./build/resources/main/META-INF/resources/"
    };
    ```
1. Copy default resources from a vanilla VueJS project with Typescript support (created with `vue create`) (or start coding your own Vue app)

    `cp -r ~/my-vue-app-with-typescript-enabled/src/* ~/my-liferay-workspace/modules/my-npm-vuejs-portlet/src/main/resources/META-INF/resources/js/`

---

# Refactor VueJS Widget to Use Webpack and Common VueJS Tooling V

1. Disable NPMREsolver in MVCPortletController:

  ```java
  ...
  public class MyNpmVuejsPortlet extends MVCPortlet {

    @Override
    public void doView(
        RenderRequest renderRequest, RenderResponse renderResponse)
      throws IOException, PortletException {

  //    renderRequest.setAttribute(
  //      "mainRequire",
  //      _npmResolver.resolveModuleName("my-npm-vuejs-portlet") + " as main");

      super.doView(renderRequest, renderResponse);
    }

  //  @Reference
  //  private NPMResolver _npmResolver;

  }
  ```
