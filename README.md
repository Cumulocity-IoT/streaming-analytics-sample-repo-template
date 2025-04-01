# Apama development container

## Overview

This repository specifies a [development container](https://containers.dev/overview), suitable for use for standard Apama development, or for working with the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk).

## Instructions

To use this, you can can either fork this repository, or copy the `.devcontainer` directory into your existing project.

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

## Legal 
Prior to executing the Docker Pull Command, downloading, using or installing the accompanying software product, please ensure to read and accept the terms applying to this offering:

[LIMITED USE LICENSE AGREEMENT FOR DOCKER IMAGES FROM CUMULOCITY GMBH](https://cumulocity.com/docs/legal-notices/limited-use-license-for-docker/)

These tools are provided as-is and without warranty or support. They do not constitute part of the Cumulocity products. Users are free to use, fork and modify them, subject to the license agreement. While Cumulocity welcomes contributions, we cannot guarantee to include every contribution in the main project.

## Questions
Ask questions at https://techcommunity.cumulocity.com/tag/streaming-analytics-apama.
