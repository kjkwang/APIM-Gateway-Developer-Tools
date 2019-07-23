# Welcome to APIM-Gateway-Developer-Tools
#### Table of Contents
* [About the Beta Release](#about-the-beta-release)
* [Features](#features)
* [Known Limitations](#known-limitations)
* [Reference Implementations](#reference-implementations)
* [Ephemeral Gateway Setup Guide](#ephemeral-gateway-setup-guide)
* [Communication](#communication)
* [How You Can Contribute](#how-you-can-contribute)
* [License](#licenses)

This GitHub repository serves as a launchpad and sitemap for the CA API Gateway developer tools and reference implementations for your organization to implement a CI/CD workflow for your Container Gateway solution development life cycle in ephemeral mode.

There are two main parts of the CI/CD workflow: local Gateway solution development (i.e., design time) and the actual CI/CD pipeline (i.e., run time) - it's important to distinguish the two as you'll be implementing the workflow in stages so that you can understand how the components work together. 

### Design Time: Local Gateway Solution Development
Design Time refers to activities pertaining to the design or development activities of Gateway policy language or services. With the Gateway Developer plugin, you build a GitOps-oriented Gateaway solution development life cycle for the Container Gateway. Design time is a precursor to run time in an Ephemeral Gateway implementation, but can also operate indepedently for non-Ephemeral Gateway implementations. Learn more in the [wiki](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki#design-time-road-to-cicd-with-gitops-oriented-local-development).

### Run Time: CI/CD Pipeline with Log Analytics and Service Metrics
Run Time refers to the activities pertaining to continuous integration, delivery, and deployment activities of the Container Gateway life cycle – automation is used where the described tools allow it. The monitoring of logs and service metrics is also included. Learn more in the [wiki](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki#run-time-cicd-pipeline-in-action-with-log-analytics-and-performance-metrics). 

## About the Beta Release
The Ephemeral Gateway is a work in progress and the contents of this Git repository is intended as a preview for any organization wanting to explore the implementation of a CI/CD workflow for their API Gateway solution development life cyle. We encourage you to give it a try and provide our development and testing teams your [valuable feedback](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/issues)! 

### Features
For this first beta release, we've focused on the following features:
* GitHub repository set up for your GitOps workflow for design time and environment configuration
* Gateway Developer Tools to propagate the import, export, and build tasks for your policies and configurations
* Integration with industry-standard CI/CD tools such as Google Kubernetes Engine, Weave Flux, Jenkins, and Nexus

### Applicability and System Requirements
For a high-level overview of the CI/CD workflow and its core components, we highly recommend that you review the [reference architecture](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Ephemeral-Gateway-Reference-Architecture) of the Ephemeral Gateway in the general Wiki.  

| Requirement | Supported/Tested in Beta Version |
| --- | --- |
| Gateway Form Factor(s) | Container Gateway Version 9.3 and newer |
| Container Orchestration Platform(s) | Google Kubernetes Engine Version 1.15 |
|Other Third Party Software | GitHub, Git, Golang, Jenkins, Weaveflux, Helm, Docker, Nexus - all latest versions as of June 2019 |

If you want to learn more about the benefits or an overview of the Ephemeral Gateway, check out our DocOps [documentation](https://docops.ca.com/ca-api-gateway/9-4/en/apis-and-toolkits/gateway-developer-plugin?src=contextnavpagetreemode).

## Known Limitations
See [Known Limitations](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Known-Limitations) in the Wiki.

## Reference Implementations
A brief description of the various GitHub repositories in CAAPIM/APIM-Gateway-Developer-Tools is described in the 
[Beta Release Respositories and Reference Implementations](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Beta-Release-Repositories-and-Reference-Implementations) wiki page. We highly recommened you to go through this link to become familiar with the various terms and repos used in this Beta release.

## Ephemeral Gateway Setup Guide
To test the beta release of the Ephemeral Gateway, follow the steps in this [master setup guide](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/ephemeral-gateway-setup-guide). From there, it'll link you to other guides to set up each component from design time (e.g, the Gateway developer Git repository) to run time (e.g, Helm Charts) in sequence. 

## Wiki Sitemap
### [Main Wiki](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki)
* Instruction Guides
  * [Ephemeral Gateway Setup Guide](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/ephemeral-gateway-setup-guide)
  * [Getting Started with the Developer Plugin](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Getting-Started-with-the-Developer-Plugin)
  * [Getting Started with Run Time](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Getting-Started-with-Runtime)
  * [Demo Gateway Setup Guide](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Demo-Gateway-Setup-Guide)
  * [Tiller Installation for Windows Users](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Tiller-Installation-for-Windows-Users)
  * [OTK Bundle Installation Guide](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/OTK-Bundle-Installation-Guide)
* Reference
  * [Ephemeral Gateway Reference Architecture](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Ephemeral-Gateway-Reference-Architecture)
  * [Beta Release Repositories and Reference Implementations](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Beta-Release-Repositories-and-Reference-Implementations)
  * [Prerequisites for Beta Testing](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Prerequisites-for-Beta-testing)
  * [Known Limitations](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Known-Limitations)
  * [Comparing the GMU Tool and Developer Plugin](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Known-Limitations)
### [Gateway Skeleton Repo Wiki](https://github.com/CAAPIM/gateway-developer-skeleton-repo/wiki)
 * [Configure Gateway Skeleton Repo](https://github.com/CAAPIM/gateway-developer-skeleton-repo/wiki/Configure-Gateway-Skeleton-Repo)
### [Gateway Developer Multi-Module Skeleton Repo Wiki](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo/wiki)
 * [Getting Started with the Multiple Module Gateway Developer Repository](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo/wiki/Getting-Started-with-the-Multiple-Module-Gateway-Developer-Repository)
### [Example Environment Configuration Repo Wiki](https://github.com/CAAPIM/example-environment-configuration-repo/wiki)
 * [Introduction to Repository and Environment Configuration](https://github.com/CAAPIM/example-environment-configuration-repo/wiki/Introduction-to-Example-Environment-Configuration-Repo)
 * [Complete Installation Instructions for Environment Configuration Repo](https://github.com/CAAPIM/example-environment-configuration-repo/wiki/Install-Instructions)
 *  [ Additional Tool Info (i.e., Weave Flux, Sealed Secrets, Misc.)](https://github.com/CAAPIM/example-environment-configuration-repo/wiki/Additional-Tools-Information)
### [Gateway Helm Charts Repo Wiki](https://github.com/CAAPIM/gateway-helm-charts/wiki)
 * [Introduction to Helm Charts](https://github.com/CAAPIM/gateway-helm-charts/wiki/Introduction-to-Gateway-Helm-Charts)
 * [Installation Instructions for Helm Charts](https://github.com/CAAPIM/gateway-helm-charts/wiki/Install-Instructions)
 * [Creating Static IP Addresses](https://github.com/CAAPIM/gateway-helm-charts/wiki/Creating-Static-IP-Addresses)
 * [Using a Private Ephemeral Gateway Skeleton Repo](https://github.com/CAAPIM/gateway-helm-charts/wiki/Using-a-Private-Ephemeral-Gateway-Skeleton-Repo)

## Communication
- *Have general questions or need help?* Use [Stack Overflow][StackOverflow]. (Tag 'cagateway')
- *Find a bug?* Open an [issue][issues] with the steps to reproduce it.
- *Want to request a feature or have an idea?* Open an [issue][issues] to tell us.

## How You Can Contribute
Contributions are welcome and much appreciated. To learn more, see the [Contribution Guidelines][contributing].

## License
Copyright (c) 2019 CA. All rights reserved.

This software may be modified and distributed under the terms
of the MIT license. See the [LICENSE][license-link] file for details.

[StackOverflow]: http://stackoverflow.com/questions/tagged/cagateway
[issues]: https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/issues
[releases]: ../../releases
[contributing]: /CONTRIBUTING.md
[license-link]: /LICENSE
