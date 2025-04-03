# Cumulocity Streaming Analytics (Apama) development container

## Overview
This repository specifies a [development container](https://containers.dev/overview), suitable for use for standard Apama development, or for working with the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) & [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools).

## Instructions
To use this, you can can either fork this repository, or copy the `.devcontainer` directory into your existing project. Use your DevContainer tool of choice (e.g. Visual Studio Code) to run this.

### Before you build
Before you build the devcontainer, you might want to adjust some of the values within `.devcontainer/devcontainer.json`.

| Parameter                             | Description                                               | Comments                                      |
| -------------                         |:-------------:                                            | -----:                                        |
| APAMA_VERSION                         | the tag of the Apama base container                       | Please see [Amazon ECR](https://gallery.ecr.aws/apama/apama-builder) for available versions  |
| APAMA_ANALYTICS_BUILDER_SDK_BRANCH    | the branch/version of the Analytics Builder SDK           | Please see [Github](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) for the available branches  |
| APAMA_EPLAPPS_TOOLS_BRANCH            | the branch/version of the EPL Apps Tools SDK              | Please see [Github](https://github.com/Cumulocity-IoT/apama-eplapps-tools) for the available branches  |

__*Note:*__ The Analytics Builder SDK needs to be in the same version as the Apama in the Cloud when you want to deploy. 

## Using Block SDK & EPLApps Tools
The Block SDK & EPLApps Tools are checked out as siblings to your current workspace folder. This allows you to easily add bundles from either of those projects using `apama_project` (which is accessible from the VSCode extension), or to simply use the, or to simply use them.

### Block SDK cloud operations
For commands in the Block SDK that require Cloud access, such as "upload", we recommend using a `.env` file.

1. Copy the `.env` file into your own repository.
2. Add it to the `.gitignore`, so you don't accidentally commit your credentials into the repository.
3. Fill out the `.env` file.
4. When you need to perform a Block SDK operation, run `source .env` within your terminal. This will create a terminal instance with the relevant environment variables for authenticating to Cumulocity.

## Legal 
Prior to executing the Docker Pull Command, downloading, using or installing the accompanying software product, please ensure to read and accept the terms applying to this offering:

[LIMITED USE LICENSE AGREEMENT FOR DOCKER IMAGES FROM CUMULOCITY GMBH](https://cumulocity.com/docs/legal-notices/limited-use-license-for-docker/)

These tools are provided as-is and without warranty or support. They do not constitute part of the Cumulocity products. Users are free to use, fork and modify them, subject to the license agreement. While Cumulocity welcomes contributions, we cannot guarantee to include every contribution in the main project.

## Questions
Ask questions at https://techcommunity.cumulocity.com/tag/streaming-analytics-apama.
