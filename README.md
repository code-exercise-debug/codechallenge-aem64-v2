# AEM 6.4 Code Challenge

This project contains source generated from the AEM Maven Archetype (version 14) and is compatible with AEM 6.3 SP1+ and AEM 6.4. For the purposes of this code challenge we will be using AEM 6.4 GA.

## Task

Create a component that would display user details returned from the API call-(Can display single user based on user id passed as queryparam)
Create an OSGi service to contact the attached API endpoint (unsecured - credentials aren't necessary) with query parameters passed.

Create a Servlet to be essentially a proxy to the service. Should return JSON with either the response from the API or an error message if not. Should have a well-formed JSON response regardless of the response. Will take URL params (via GET) to pass options to the service.

All of the required Maven dependencies have been added to the project already.

API URL: https://jsonplaceholder.typicode.com/users

## Modules

The main parts of the project are:

* core: Java bundle containing all core functionality like OSGi services, listeners or schedulers, as well as component-related Java code such as servlets or request filters.
* ui.apps: contains the /apps (and /etc) parts of the project, ie JS&CSS clientlibs, components, templates, runmode specific configs as well as Hobbes-tests
* ui.content: contains sample content using the components from the ui.apps
* ui.tests: Java bundle containing JUnit tests that are executed server-side. This bundle is not to be deployed onto production.
* ui.launcher: contains glue code that deploys the ui.tests bundle (and dependent bundles) to the server and triggers the remote JUnit execution
