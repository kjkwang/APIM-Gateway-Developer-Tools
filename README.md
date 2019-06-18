# APIM-Gateway-Developer-Tools
Get started with APIM Gateway Developer Tools and CI/CD Reference Implementations

## Get Started
Check out our [documentation](https://docops.ca.com/ca-api-gateway/9-4/en/apis-and-toolkits/gateway-developer-plugin?src=contextnavpagetreemode) for sample code, video tutorials, and more.  

## Gateway Developer Tools Framework
Gateway Developer Tools consist of these frameworks:

- [gateway-developer-plugin](https://github.com/CAAPIM/gateway-developer-plugin)

For more information about our Gateway Developer Tool visit [developer website](https://docops.ca.com/ca-api-gateway/9-4/en/apis-and-toolkits/gateway-developer-plugin?src=contextnavpagetreemode).

## Features

* **gateway-developer-plugin** - Reads configuration files, converts them to the Gateway Restman bundle format and builds the GW7 package.	

* **gateway-export-plugin** - Exports current configurations from an existing Gateway, converts them into the plugin format, and stores it in the local directory structure, allowing for pushing to a VCS system.	

* **gateway-import-plugin** - Imports and installs generated solutions to an existing running Gateway. Used primarily for transitioning Gateways from an appliance to a container form factor.	

* **environment-creator application** - Part of the the GW7 package and used for deployment, this tool collects all environment properties that are relevant to the container and applies their values to the bundles. It is run before Container Gateway startup.

## Installation
Edit your build.gradle file and add below dependency:

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

## SDK Releases
The compiled release binaries can be found here: [Releases][Releases]

## Sample Apps
**All sample apps have moved to GITHub as of 1.6.00 release. Links will redirect to the latest released versions.**

- [gateway-developer-skeleton-repo](https://github.com/CAAPIM/gateway-developer-skeleton-repo)
- [gateway-developer-multimodule-skeleton-repo](https://github.com/CAAPIM/gateway-developer-multimodule-skeleton-repo)
- [gateway-metrics-grafana-example](https://github.com/CAAPIM/gateway-metrics-grafana-example)
- [gateway-tic-tac-toe](https://github.com/CAAPIM/gateway-tic-tac-toe)
- [template-policies](https://github.com/CAAPIM/template-policies)

## Communication
- *Have general questions or need help?*, use [Stack Overflow][StackOverflow]. (Tag 'massdk')
- *Find a bug?*, open an [issue][issues] with the steps to reproduce it.
- *Request a feature or have an idea?*, open an [issue][issues].

## How You Can Contribute
Contributions are welcome and much appreciated. To learn more, see the [Contribution Guidelines][contributing].

## Documentation
For more documentation including API references, go to our [main website][docs].

## License
Copyright (c) 2017 CA. All rights reserved.

This software may be modified and distributed under the terms
of the MIT license. See the [LICENSE][license-link] file for details.

[mag]: https://docops.ca.com/mag
[mas.ca.com]: http://mas.ca.com/
[docs]: http://mas.ca.com/docs/
[blog]: http://mas.ca.com/blog/
[get-started]: http://mas.ca.com/get-started
[StackOverflow]: http://stackoverflow.com/questions/tagged/massdk
[issues]: https://github.com/CAAPIM/Android-MAS-SDK/issues
[releases]: ../../releases
[contributing]: /CONTRIBUTING.md
[license-link]: /LICENSE
[video]: https://www.ca.com/us/developers/mas/videos.html
[documentation]: https://www.ca.com/us/developers/mas/docs.html
