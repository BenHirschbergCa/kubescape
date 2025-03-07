[![Version](https://img.shields.io/github/v/release/kubescape/kubescape)](https://github.com/kubescape/kubescape/releases)
[![build](https://github.com/kubescape/kubescape/actions/workflows/02-release.yaml/badge.svg)](https://github.com/kubescape/kubescape/actions/workflows/02-release.yaml)
[![Go Report Card](https://goreportcard.com/badge/github.com/kubescape/kubescape)](https://goreportcard.com/report/github.com/kubescape/kubescape)
[![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-Ready--to--Code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/kubescape/kubescape)
[![GitHub](https://img.shields.io/github/license/kubescape/kubescape)](https://github.com/kubescape/kubescape/blob/master/LICENSE)
[![CNCF](https://shields.io/badge/CNCF-Sandbox%20project-blue?logo=linux-foundation&style=flat)](https://landscape.cncf.io/card-mode?project=sandbox&selected=kubescape)
[![Artifact HUB](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/kubescape)](https://artifacthub.io/packages/search?repo=kubescape)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fkubescape%2Fkubescape.svg?type=shield&issueType=license)](https://app.fossa.com/projects/git%2Bgithub.com%2Fkubescape%2Fkubescape?ref=badge_shield&issueType=license)
[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/6944/badge)](https://www.bestpractices.dev/projects/6944)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/kubescape/kubescape/badge)](https://securityscorecards.dev/viewer/?uri=github.com/kubescape/kubescape)
[![Stars](https://img.shields.io/github/stars/kubescape/kubescape?style=social)](https://github.com/kubescape/kubescape/stargazers)
[![Twitter Follow](https://img.shields.io/twitter/follow/kubescape?style=social)](https://twitter.com/kubescape)
[![Slack](https://img.shields.io/badge/slack-kubescape-blueviolet?logo=slack)](https://cloud-native.slack.com/archives/C04EY3ZF9GE)

# Kubescape

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/cncf/artwork/master/projects/kubescape/stacked/white/kubescape-stacked-white.svg" width="150">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/cncf/artwork/master/projects/kubescape/stacked/color/kubescape-stacked-color.svg" width="150">
  <img alt="Kubescape logo" align="right" src="https://raw.githubusercontent.com/cncf/artwork/master/projects/kubescape/stacked/color/kubescape-stacked-color.svg" width="150">
</picture>

_Comprehensive Kubernetes Security from Development to Runtime_

Kubescape is an open-source Kubernetes security platform that provides comprehensive security coverage from left to right across the entire development and deployment lifecycle. It offers hardening, posture management, and runtime security capabilities to ensure robust protection for Kubernetes environments.

**Key features of Kubescape include**

* **Shift-left security**: Kubescape enables developers to scan for misconfigurations as early as the manifest file submission stage, promoting a proactive approach to security.  
* **IDE and CI/CD integration**: The tool integrates seamlessly with popular IDEs like VSCode and Lens, as well as CI/CD platforms such as GitHub and GitLab, allowing for security checks throughout the development process.
* **Cluster scanning**: Kubescape can scan active Kubernetes clusters for vulnerabilities, misconfigurations, and security issues
* **Multiple framework support**: Kubescape can test against various security frameworks, including NSA, MITRE, SOC2, and more.
* **YAML and Helm chart validation**: The tool checks YAML files and Helm charts for correct configuration according to the frameworks above, without requiring an active cluster.
* **Kubernetes hardening**: Kubescape ensures proactive identification and rapid remediation of misconfigurations and vulnerabilities through manual, recurring, or event-triggered scans.
* **Runtime security**: Kubescape extends its protection to the runtime environment, providing continuous monitoring and threat detection for deployed applications.
* **Compliance management**: The tool aids in maintaining compliance with recognized frameworks and standards, simplifying the process of meeting regulatory requirements.
* **Multi-cloud support**: Kubescape offers frictionless security across various cloud providers and Kubernetes distributions.

By providing this comprehensive security coverage from development to production, Kubescape enables organizations to implement a robust security posture throughout their Kubernetes deployment, addressing potential vulnerabilities and threats at every stage of the application lifecycle.

Kubescape was created by [ARMO](https://www.armosec.io/?utm_source=github&utm_medium=repository) and is a [Cloud Native Computing Foundation (CNCF) sandbox project](https://www.cncf.io/sandbox-projects/).

_Please [star ⭐](https://github.com/kubescape/kubescape/stargazers) the repo if you want us to continue developing and improving Kubescape! 😀_

## Demo

Kubescape has a command line tool that you can use to quickly get a report on the security posture of a Kubernetes cluster:

<img src="docs/img/demo-v3.gif">

## Getting started

Experimenting with Kubescape is as easy as:

```sh
curl -s https://raw.githubusercontent.com/kubescape/kubescape/master/install.sh | /bin/bash
```

This script will automatically download the latest Kubescape CLI release and scan the Kubernetes cluster in your current kubectl context.

Learn more about:

* [Installing the Kubescape CLI](https://kubescape.io/docs/install-cli/)
* [Running your first scan](https://kubescape.io/docs/scanning/)
* [Accepting risk with exceptions](https://kubescape.io/docs/accepting-risk/)

_Did you know you can use Kubescape in all these places?_

<div align="center">
    <img src="docs/img/ksfromcodetodeploy.png" alt="Places you can use Kubescape: in your IDE, CI, CD, or against a running cluster.">
</div>

### Continuous security monitoring with the Kubescape Operator

As well as a CLI, Kubescape provides an in-cluster mode, which is installed via a Helm chart. Kubescape in-cluster provides extensive features such as continuous scanning, image vulnerability scanning, runtime analysis, network policy generation, and more. [Learn more about the Kubescape operator](https://kubescape.io/docs/operator/).

### Using Kubescape as a GitHub Action

Kubescape can be used as a GitHub Action. This is a great way to integrate Kubescape into your CI/CD pipeline. You can find the Kubescape GitHub Action in the [GitHub Action marketplace](https://github.com/marketplace/actions/kubescape).

## Under the hood

Kubescape uses [Open Policy Agent](https://github.com/open-policy-agent/opa) to verify Kubernetes objects against [a library of posture controls](https://github.com/kubescape/regolibrary). Kubescape retrieves Kubernetes resources from the API server and runs a set of [Rego snippets](https://www.openpolicyagent.org/docs/latest/policy-language/) developed by [ARMO](https://www.armosec.io?utm_source=github&utm_medium=repository).

Container image scanning is powered by [Grype](https://github.com/anchore/grype) and image patching uses [Copacetic](https://github.com/project-copacetic/copacetic).

By default, CLI scan results are printed in a console-friendly manner, but they can be:

* exported to JSON, junit XML or SARIF
* rendered to HTML or PDF
* submitted to a [cloud service](docs/providers.md)

### In-cluster architecture 

![Architecture diagram](docs/img/architecture-diagram.png)

## Community

We welcome user feedback and ideas for improvement.

Kubescape users and developers meet on the CNCF Slack. [Join it](https://slack.cncf.io/) and find us in [#kubescape](https://cloud-native.slack.com/archives/C04EY3ZF9GE) or [#kubescape-dev](https://cloud-native.slack.com/archives/C04GY6H082K).

We hold [community meetings](https://zoom.us/j/95174063585) on Zoom, every second Tuesday, at 15:00 CET. ([See that in your local time zone](https://time.is/compare/1500_in_CET). 

* Meetings are announced in [#kubescape-dev](https://cloud-native.slack.com/archives/C04GY6H082K) on Slack (including any cancellations).
* [The agenda and notes are in a public Google doc](https://docs.google.com/document/d/1X_eyhPzJvb4ascVQ2e0jN87LAvq7lTuXT5d4gQxi8us/edit?tab=t.0).
* [Recordings are posted to YouTube](https://www.youtube.com/@kubescape).

The Kubescape project follows the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

### Adopters

See [here](ADOPTERS.md) for a list of reference adopters.

### Contributions

Thanks to all our contributors!  Check out our [CONTRIBUTING](CONTRIBUTING.md) file to learn how to join them.

* Feel free to pick a task from the [issues](https://github.com/kubescape/kubescape/issues?q=is%3Aissue+is%3Aopen+label%3A%22open+for+contribution%22), [roadmap](docs/roadmap.md) or suggest a feature of your own.
* [Open an issue](https://github.com/kubescape/kubescape/issues/new/choose): we aim to respond to all issues within 48 hours.

<br>

<a href = "https://github.com/kubescape/kubescape/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=kubescape/kubescape"/>
</a>

## Changelog

Kubescape changes are tracked on the [release](https://github.com/kubescape/kubescape/releases) page.

## License

Copyright 2021-2024, the Kubescape Authors. All rights reserved. Kubescape is released under the Apache 2.0 license. See the [LICENSE](LICENSE) file for details.

Kubescape is a [Cloud Native Computing Foundation (CNCF) sandbox project](https://www.cncf.io/sandbox-projects/) and was contributed by [ARMO](https://www.armosec.io/?utm_source=github&utm_medium=repository).

<div align="center">
    <img src="https://raw.githubusercontent.com/cncf/artwork/master/other/cncf-sandbox/horizontal/color/cncf-sandbox-horizontal-color.svg" width="300" alt="CNCF Sandbox Project">
</div>
