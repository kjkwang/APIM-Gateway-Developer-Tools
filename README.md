# Getting Started with APIM-Gateway-Developer-Tools
This GitHub repository contains the required CA API Gateway developer tools and CI/CD reference implementations for your organization to implement a CI/CD workflow that optimizes both the design and run times of the Container Gateway life cycle in ephemeral mode. 

Design time refers to activities pertaining to the design or development activities of Gateway policy language while run time refers to the activities pertaining to delivery, integration, and deployment activities of the Container Gateway life cycle – automation is used where the described tools allow it.

## About the Beta Release
The Ephemeral Gateway is a work in progress and the contents of this Git repository is intended as a preview for any organization wanting to explore the implementation of a CI/CD workflow for their API Gateway solution development life cyle. We encourage you to give it a try and provide our development and testing teams your valuable feedback! 

If you want to learn more about the benefits or an overview of the Ephemeral Gateway, check out our DocOps [documentation](https://docops.ca.com/ca-api-gateway/9-4/en/apis-and-toolkits/gateway-developer-plugin?src=contextnavpagetreemode).

Before diving into the individual developer tools, check out the general Wiki page to learn the basic setup for your Ephemeral Gateway, and a reference architecture. 

## Gateway Developer Tools Framework
Gateway Developer Tools consist of these frameworks:

- [gateway-developer-plugin](https://github.com/CAAPIM/gateway-developer-plugin)
- [gateway-export-plugin](https://github.com/CAAPIM/gateway-developer-plugin/tree/master/gateway-export-plugin)
- [gateway-import-plugin](https://github.com/CAAPIM/gateway-developer-plugin/tree/master/gateway-import-plugin)

For more information about our Gateway Developer Tool visit [developer website](https://docops.ca.com/ca-api-gateway/9-4/en/apis-and-toolkits/gateway-developer-plugin?src=contextnavpagetreemode).

## Features

* **gateway-developer-plugin** - Reads configuration files, converts them to the Gateway Restman bundle format and builds the GW7 package.	

* **gateway-export-plugin** - Exports current configurations from an existing Gateway, converts them into the plugin format, and stores it in the local directory structure, allowing for pushing to a VCS system.	

* **gateway-import-plugin** - Imports and installs generated solutions to an existing running Gateway. Used primarily for transitioning Gateways from an appliance to a container form factor.	

* **environment-creator application** - Part of the the GW7 package and used for deployment, this tool collects all environment properties that are relevant to the container and applies their values to the bundles. It is run before Container Gateway startup.

## Known Limitations
As we push forward to providing the best product and high Time-to-Value with the Ephemeral Gateway, please be aware of the following limitations for this beta release when testing for your own implementation:
* Policy Manager access to a Kubernetes Gateway cluster is disabled.
* The following Gateway entities have been tested for the Gateway Developer Plugin:
  * Cassandra Connections
  * Encapsulated Assertions
  * Identity Providers
  * JDBC Connections
  * JMS Destinations
  * Listen Ports
  * Policy Backed Services
  * Private Keys
  * Scheduled Tasks
  * Services
  * Static Properties
  * Stored Passwords
  * Trusted Certificates
  All other entities shall be tested in gradual phases, post-beta. 
* Environment variable names in a Kubernetes pod container do not accept spaces in names - this may cause issues for any Gateway environmental values with spaces exported to a pod container in Kubernetes (i.e., the pod container will not start). 

## Installation
Edit your build.gradle file and add the following dependency:

```groovy
plugins {
    id "com.ca.apim.gateway.gateway-developer-plugin" version "0.8.+"
    id "com.ca.apim.gateway.gateway-export-plugin" version "0.8.+"
}

repositories {
    // This is needed in order to get dependencies for the environment 
    // creator application that is bundled in the gw7 file.
    mavenCentral()
}

// The Gateway Export Config is needed by the gateway-export plugin in order to export from a gateway
GatewayExportConfig {
    folderPath = '/my-solution-folder'
}

// The Gateway Connection Config is required if setting mentioned in main [build.gradle](https://github.com/ca-api-gateway-examples/gateway-developer-example/blob/master/build.gradle) is not applicable to this folder.
GatewayConnection {
    url = 'https://<gateway-host>:8443/restman'
}
```

## Releases
The compiled release binaries can be found here: [Releases][Releases]

## Sample Apps
**Links will redirect to the latest released versions.**

- [gateway-developer-skeleton-repo](https://github.com/CAAPIM/gateway-developer-skeleton-repo)
- [gateway-developer-multimodule-skeleton-repo](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo)
- [gateway-metrics-grafana-example](https://github.com/CAAPIM/gateway-metrics-grafana-example)
- [gateway-tic-tac-toe](https://github.com/CAAPIM/gateway-tic-tac-toe)
- [template-policies](https://github.com/CAAPIM/template-policies)
- [environment-configuration-repo](https://github.com/CAAPIM/example-environment-configuration-repo)

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
