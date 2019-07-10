# Getting Started with APIM-Gateway-Developer-Tools
This GitHub repository contains the required CA API Gateway developer tools and CI/CD reference implementations for your organization to implement a CI/CD workflow that optimizes both the design and run times of the Container Gateway life cycle in ephemeral mode. 

Design time refers to activities pertaining to the design or development activities of Gateway policy language while run time refers to the activities pertaining to delivery, integration, and deployment activities of the Container Gateway life cycle – automation is used where the described tools allow it.

#### Table of Contents
* [About the Beta Release](#about-the-beta-release)
* [Gateway Developer Tools Framework](#gateway-developer-tools-framework)
* [Features](#features)
* [Known Limitations](#known-limitations)
* [Installation](#installation)
* [Releases](#releases)
* [Reference Implementations](#reference-implementations)
* [Communication](#communication)
* [How You Can Contribute](#how-you-can-contribute)
* [License](#licenses)

## About the Beta Release
The Ephemeral Gateway is a work in progress and the contents of this Git repository is intended as a preview for any organization wanting to explore the implementation of a CI/CD workflow for their API Gateway solution development life cyle. We encourage you to give it a try and provide our development and testing teams your valuable feedback! 

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

## Gateway Developer Tools Framework
Gateway Developer Tools consist of these frameworks:

| Tool | Function |
| --- | --- |
| [gateway-developer-plugin](https://github.com/CAAPIM/gateway-developer-plugin) |Reads configuration files, converts them to the Gateway Restman bundle format and builds the GW7 package.|
|[gateway-export-plugin](https://github.com/CAAPIM/gateway-developer-plugin/tree/master/gateway-export-plugin) |Exports current configurations from an existing Gateway, converts them into the plugin format, and stores it in the local directory structure, allowing for pushing to a VCS system.|
|[gateway-import-plugin](https://github.com/CAAPIM/gateway-developer-plugin/tree/master/gateway-import-plugin)|Imports and installs generated solutions to an existing running Gateway. Used primarily for transitioning Gateways from an appliance to a container form factor.|
|[environment-creator application](https://github.com/CAAPIM/gateway-developer-plugin/tree/master/environment-creator-application)| Part of the the GW7 package and used for deployment, this tool collects all environment properties that are relevant to the container and applies their values to the bundles. It is run before Container Gateway startup.|


Before diving into the individual developer tools, check out the [general Wiki page](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki) to learn the basic setup for your Ephemeral Gateway, and a reference architecture. 
## Known Limitations
See [Known Limitations](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/Known-Limitations) in the Wiki.

## Installation 
### Prerequisites for Policy Developers
1. Have Docker installed.
2. Have an existing Gateway license
3. A running Gateway which has a policy to export. As an example for this getting started guide. You can find it at [Getting Started Gateway](https://github.com/J-Lou/getting-started-developer-plugin). To boot up your running Getting Started Gateway, instructions are provided below.
    1. Open up a terminal in the base directory of the `Getting Started Gateway`.
    2. Place a license in `docker/`
    3. Execute the following commands.
    ```console
    $ ./gradlew clean build
    $ docker-compose up --force-recreate
    ```
    **Note**: The IP address of this Gateway is https://localhost:844

### Installation Guides on the Wiki

#### Design Time
* [Sample Gateway Project to Export to GitOps](https://github.com/J-Lou/getting-started-developer-plugin)

* [Single Module Installation Guide](https://github.com/CAAPIM/gateway-developer-skeleton-repo/wiki/1.-Getting-Started-with-the-Gateway-Developer-Repository) 

* [Multi Module Installation Guide](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo/wiki/1.-Getting-Started-with-the-Multiple-Module-Gateway-Developer-Repository)

* [OTK Bundle Installation Guide](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/3.-OTK-Bundle-Installation-Guide)

#### Run Time

* [Getting Started with Run Time](https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/wiki/2.-Getting-Started-with-Runtime)
* [Setting Up for Jenkins Build](https://github.com/CAAPIM/ephemeral-gateway-skeleton-repo/wiki/Setting-up-for-Jenkins-Build)


## Releases
The compiled release binaries can be found here: [Releases][Releases]

## Reference Implementations
**Links will redirect to the latest released versions.**

| Repository | Description|
| --- | --- |
| [gateway-developer-skeleton-repo](https://github.com/CAAPIM/gateway-developer-skeleton-repo) |Reads configuration files, converts them to the Gateway Restman bundle format and builds the GW7 package.|
|[ephemeral-gateway-skeleton-repo](https://github.com/CAAPIM/ephemeral-gateway-skeleton-repo)|Exports current configurations from an existing Gateway, converts them into the plugin format, and stores it in the local directory structure, allowing for pushing to a VCS system.|
|[gateway-developer-multimodule-skeleton-repo](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo)|Imports and installs generated solutions to an existing running Gateway. Used primarily for transitioning Gateways from an appliance to a container form factor.|
|[gateway-tic-tac-toe](https://github.com/CAAPIM/gateway-tic-tac-toe)| Part of the the GW7 package and used for deployment, this tool collects all environment properties that are relevant to the container and applies their values to the bundles. It is run before Container Gateway startup.|
|[gateway-metrics-grafana-example](https://github.com/CAAPIM/gateway-metrics-grafana-example)|asd|
|[template-policies](https://github.com/CAAPIM/template-policies)|asdf|
|[environment-configuration-repo](https://github.com/CAAPIM/example-environment-configuration-repo)|asdf


## Communication
- *Have general questions or need help?* Use [Stack Overflow][StackOverflow]. (Tag 'cagateway')
- *Find a bug?* Open an [issue][issues] with the steps to reproduce it.
- *Want to request a feature or have an idea?* Open an [issue][issues] to tell us.

## How You Can Contribute
Contributions are welcome and much appreciated. To learn more, see the [Contribution Guidelines][contributing].

## Documentation
For more documentation on the CA API Gateway, visit our [DocOps](https://docops.ca.com/gateway) site. 

## License
Copyright (c) 2019 CA. All rights reserved.

This software may be modified and distributed under the terms
of the MIT license. See the [LICENSE][license-link] file for details.


[StackOverflow]: http://stackoverflow.com/questions/tagged/cagateway
[issues]: https://github.com/CAAPIM/APIM-Gateway-Developer-Tools/issues
[releases]: ../../releases
[contributing]: /CONTRIBUTING.md
[license-link]: /LICENSE
