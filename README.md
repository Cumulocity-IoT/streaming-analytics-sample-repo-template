# Apama development container

## Purpose & how to use

This repository specifies a [development container](https://containers.dev/overview), suitable for use for standard Apama development, or for working with the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk).

You can either fork this repository, or copy the `.devcontainer` directory into your existing project.


## Instructions

### Pre-requisites for Block SDK development
If you are using this for [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) development, you will need a Cumulocity Cloud tenant, with Streaming Analytics and Analytics Builder subscriber. 

For regular Apama development, you do not need this configured.

### Before you build
Before you build the devcontainer within Visual Studio Code you should take a look at the devcontainer.json and adjust the build parameters and environment variables.

| Parameter                             | Description                                               | Comments                                      |
| -------------                         |:-------------:                                            | -----:                                        |
| APAMA_VERSION                         | the tag of the Apama base container                       | Please see docker hub for available versions  |
| APAMA_ANALYTICS_BUILDER_SDK_BRANCH    | the branch/version of the Analytics Builder SDK           | Please see [Github](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) for the available branches  |
| CUMULOCITY_SERVER_URL                 | The Cumulocity IoT instance to connect to                 |                                               |
| CUMULOCITY_TENANT                     | The tenantId of your Cumulocity IoT tenant                |                                               |
| CUMULOCITY_USERNAME                   | The username of your Cumulocity IoT user                  |                                               |
| CUMULOCITY_PASSWORD                   | The username of your Cumulocity IoT password              |                                               |
| CUMULOCITY_APPKEY                     | The application key the local Apama will use for testing  |                                               |

__*Note:*__

*The Analytics Builder SDK needs to be in the same version as the Apama in the Cloud when you want to deploy. Therefore it also recommended to use the same Apama version in the devcontainer (e.g. if the Cloud is in version 10.7 the same versions should be used in the devcontainer for both Apama and SDK).*

### Starting in Visual Studio Code
After you finsihed the configuration you can click the devcontainer icon in the bottom left of Visual Studio Code and select `Open Folder in Container...`.
Once the container has been built and started you should see four folders in your VCS workspace:
1. Development (the contents of this repository)
2. Analytics Builder SDK
3. Analytics Builder SDK Documentation
4. Apama

## Analytics Builder Development

Please check the SDK documentation for more detailed instructions.

### Testing
You can find an example pysys project under `Development -> example`. Simply navigate to the folder where the `pysysproject.xml` is located and run `pysys test`.

### Deploying to Cumulocity IoT
In order to deploy your blocks to your Cumulocity IoT tenant you can simply run `apama blocks deploy <extensionName>` from the folder where your blocks are located ( the .mon files). The extensionName can be freely chosen. You can try it out by navigating to `Development -> example -> blocks` and run the command from there.

### Undeploying from Cumulocity IoT
In order to remove your blocks again from your Cumulocity IoT tenant just run `apama blocks undeploy <extensionName>`. The extensionName has to be the same as you used when deploying.

---

These tools are provided as-is and without warranty or support. They do not constitute part of the Cumulocity products. Users are free to use, fork and modify them, subject to the license agreement. While Cumulocity welcomes contributions, we cannot guarantee to include every contribution in the main project.
_____________
Contact us at https://apamacommunity.com if you have any questions.
