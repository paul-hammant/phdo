---
layout: page
title: HedgeServ innovations
permalink: /HedgeServ-Innovations
tags:
  - Trunk-Based Development
  - Service Virtualization
  - Continuous Delivery
  - Speedy Builds
---

In 2014 I left ThoughtWorks and joined HedgeServ, a leading hedge fund administrator, in Manhattan. I started as Senior
Director of Engineering, overseeing 68 highly-skilled developers and QAs and left as Chief Science Officer at the end
of 2016. I enjoyed my time at HedgeServ, and would highly recommend it for someone wanting to get into Fin-Tech, and
experience the pressure for increased release cadence and the problem solving to get there.

I was very pleased to find when I arrived that HedgeServ was already doing Trunk Based Development, and only required
a small tweak to their workflow.

## New applications

My achievements include the spinning up of four projects (3 applications, 1 service), with fast builds that followed
the 'test pyramid' closely with a suite of Selenium tests close out the build (for the 3 UI ones). Three of the four
new apps used Service Virtualization (SV) in the build in order be speedy.

In one particular case **the build time for compile, unit tests, integration tests, and Selenium tests was 30 seconds**,
and each commit would reach UAT, using Chef scripts to handle the deployment. Business leadership was appreciative of
the faster cycle times. The solution was Java and AngularJS, and the fire-hose into UAT could be adjusted to allow an
audit-approved sign-off sequence before go-live, that used Chef scripts to verify the approvals.

## DevOps pieces

### Monolith split into Micro applications.

I also redesigned and oversaw the rework of the web tier's codebase to have separations between the different web
applications so that they could fit a Google style of site composition[^tnav] (including authentication). The different
apps had to agree on URLs, cookies, redirects in order to be stitched together into a single site experience by the
load balancer. This allowed each to have separate release cadences, and different modernization and investment backlogs
and emphasis.

[^tnav]: [How Google makes a consistent top-navigation across multiple apps](https://paulhammant.com/2015/07/13/how-google-makes-a-consistent-top-navigation-across-multiple-apps/) (Jul, 2015, my blog)

### Test execution reduction via impact mapping

This most recently detailed on Martin Fowler's website as [a guest posting](https://martinfowler.com/articles/rise-test-impact-analysis.html).

I pioneered techniques to advance calculate the impacted tests for a commit and only run those, as a quicker proof
of correctness. I went as far as to provide the proofs of concept in Java[^jtr] and Python[^ptr], and it is been
productionized since I left.  This is a general purpose solution: In a perpetually running CI daemon is running one
test at a time, and working out what prod code was covered, then reversing it to store it in a map, which itself
is represented in text and committed. Later, with a given change set (one or more commits) in regular CI, only impacted
tests are run, for a greatly shortened test suite run. Microsoft is doing some impacted test reduction their ALM
features of Visual Studio[^ms1]<sup>,</sup>[^ms2], but it is unclear whether it is to do with code-coverage mappings.

[^jtr]: [Reducing Test Times by Only Running Impacted Tests](https://paulhammant.com/2015/01/11/reducing-test-times-by-only-running-impacted-tests/) (Jan, 2015, my blog)
[^ptr]: [Reducing Test Times by Only Running Impacted Tests - Python Edition](https://paulhammant.com/2015/01/18/reducing-test-times-by-only-running-impacted-tests-python-edition/) (Jan, 2015,my blog)
[^ms1]: [Accelerated Continuous Testing with Test Impact Analysis – Part 1](https://blogs.msdn.microsoft.com/visualstudioalm/2017/03/02/accelerated-continuous-testing-with-test-impact-analysis-part-1/) (Mar, 2017, Microsoft)
[^ms2]: [Accelerated Continuous Testing with Test Impact Analysis – Part 2](https://blogs.msdn.microsoft.com/visualstudioalm/2017/05/16/accelerated-continuous-testing-with-test-impact-analysis-part-2/) (May, 2017, Microsoft)

<!-- ### New Config as Code system -->

<!-- Lastly, I invented a system to store client configuration in source-control allowing UI editing and publishing through
the multiple affected server nodes when changed. I'm not sure of the status of that since leaving. -->

