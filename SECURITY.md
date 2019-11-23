# Security Policies and Procedures

This document outlines security procedures and general policies for this project.

## Reporting a Bug

This project's team and community take all security bugs and vulnerabilities seriously. Thank you for taking the time
to improve the security of this project. We appreciate your efforts and, we will make every effort to acknowledge your
contributions.

Report security bugs by emailing [the lead contributor][lead-email] with information about the vulnerability.

A core contributor will acknowledge your issue, and they will respond appropriately depending on the severity, impact,
and risk of the scope reported. After your initial report, the security team will endeavor to keep you informed of the
progress towards a fix and full announcement, and they may ask for additional information or guidance. You can also
reach out to the person directly on the project's [Gitter space][gitter].

### Third-Party Vulnerabilities

Please report security bugs in third-party modules to the person or team maintaining the module.

### Node Security Project

As this is a node-based project, you can also report a vulnerability through the
[Node Security Project][node-security] (now npm.js).

## Disclosure Policy

When the security team receives a security bug report, they will assign it to a primary handler. This person will
confirm the report, coordinate the fix, and manage the release process, involving the following steps:

* Confirm the problem and determine the affected versions; and,
* Audit code to find any potential similar problems; and,
* Prepare fixes for all releases still under maintenance.

## Critical Updates and Security Notices

We regularly run static code analysis to determine need for critical software updates and security threats from these
sources:

* [GitHub Security Alerts][github-alerts]
* [TravisCI][travisci]

## Comments on this Policy

If you have suggestions on how this process could be improved please submit a Pull Request for this documentation.




[lead-email]:    mailto:hello@andrewvaughan.io?subject=GitHub%20generator-andrewvaughan%20Security%20Report

[github-alerts]: https://help.github.com/en/github/managing-security-vulnerabilities/about-security-alerts-for-vulnerable-dependencies
[gitter]:        https://gitter.im/andrewvaughan/generator
[node-security]: https://docs.npmjs.com/reporting-a-vulnerability-in-an-npm-package
[travisci]:      https://travis-ci.org
