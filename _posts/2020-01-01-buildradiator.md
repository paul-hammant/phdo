---
layout: page
title: Build Radiators as a Service
permalink: /Build-Radiators-as-a-Service
tags:
  - Continuous Integration
---

After a number of assessments where one my recommendations was to "have a build radiator on a wall, and use the social engineering to get the build to consistently pass", I realized that corporates have a bunch of hurdles to overcome. Two key InfoSec concerns for a radiator are:

1. Every device with a screen on the LAN has to be logged in as a real employee
2. Screensavers for employees cannot be turned off

So it occurred to me that mounting a SmartTV in the guest WiFi without an associated user account, with a browser showing a 'public' site was the way to go. The site has a little bit of real security and a lot of 'security though obscurity', which helps to push past the corporate objections.

Thus the [BuildRadiator.org site](https://buildradiator.org) was born:

![Radiator pic](https://cloud.githubusercontent.com/assets/82182/26152799/8c69e2f0-3ad6-11e7-8294-62196ebad748.png)

People can make their own private radiator there, and start using it within seconds. Indeed, [BuildRadiator](https://github.com/BuildRadiator/BuildRadiator) (the project behind BuildRadiator&#46;org) has its own build radiator on BuildRadiator&#46;org [here](https://buildradiator.org/r#b7n63m6hcb9sm2ttdn/Build_Radiator_DotOrg_Master), with CircleCI faithfully running builds and pushing build/step changes as they happen.

From a DevOps point of view, the project itself is mildly interesting. Java + Vue.js with **a build time for compile, unit tests, integration tests, and Selenium tests of 35 seconds**. Jooby is the server framework, and it is a breath of fresh air compared to Java technologies from previous years.

Note: A build radiator is one type of "information radiator", and the Agile Alliance speaks to those when it says "Intensive use of information radiators conveys two messages in addition to the information itself"[^ir], and caveats:

* the team has nothing to hide from its visitors (customers, stakeholders...)
* the team has nothing to hide from itself: it acknowledges and confronts problems

[^ir]: [Information Radiators](https://www.agilealliance.org/glossary/information-radiators/)


