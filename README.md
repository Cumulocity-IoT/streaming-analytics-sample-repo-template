# Cumulocity Streaming Analytics (Apama) development container

## Overview
This repository specifies a [development container](https://containers.dev/overview), suitable for use for standard Apama development, or for working with the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) & [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools).

## Instructions
To use this, you can either fork this repository, or copy the `.devcontainer` directory into your existing project. Use your DevContainer tool of choice (e.g. [Visual Studio Code](https://code.visualstudio.com/docs/devcontainers/containers)) to run this.

### Before you build
Before you build the devcontainer, you might want to adjust some of the values within `.devcontainer/devcontainer.json`.

| Parameter                             | Description                                               | Comments                                      |
| -------------                         |:-------------:                                            | -----:                                        |
| APAMA_IMAGE                           | the Apama Docker image to use                             | Please see [Amazon ECR](https://gallery.ecr.aws/apama) for available images. Note: on versions older than 26, we advise using `public.ecr.aws/apama/apama-cumulocity-builder`. | 
| APAMA_VERSION                         | the tag of the Apama base container                       | Please see [Amazon ECR](https://gallery.ecr.aws/apama/apama-builder) for available versions.  |
| APAMA_ANALYTICS_BUILDER_SDK_BRANCH    | the branch/version of the Analytics Builder SDK           | Please see [Github](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) for the available branches  |
| APAMA_EPLAPPS_TOOLS_BRANCH            | the branch/version of the EPL Apps Tools SDK              | Please see [Github](https://github.com/Cumulocity-IoT/apama-eplapps-tools) for the available branches  |

__*Note:*__ The Analytics Builder SDK needs to be in the same version as the Apama in the Cloud when you want to deploy. 

## Using Block SDK & EPLApps Tools
The Block SDK & EPLApps Tools are checked out as siblings to your current workspace folder. This allows you to easily add bundles from either of those projects using `apama_project` (which is accessible from the VSCode extension), or to simply use the, or to simply use them.

### Block SDK cloud operations
For commands in the Block SDK that require Cloud access, such as "upload", we recommend using a `.env` file.

1. Add `.env` to your `.gitignore` file.
2. Create a `.env` file with the following format.

```
CUMULOCITY_SERVER_URL=<URL>
CUMULOCITY_USERNAME=<USERNAME>
CUMULOCITY_PASSWORD=<PASSWORD>
```

Replacing `<URL>`, `<USERNAME>` and `<PASSWORD>` with the correct values.

3. When you need to perform a Block SDK operation, run `source .env` within your terminal. This will create a terminal instance with the relevant environment variables for authenticating to Cumulocity.


## Usage notes
- You may find the default memory allocated by your containerization tool is not sufficient. We advise having a minimum of 4GB of memory for local development. 

## Legal notices
Prior to executing the Docker Pull Command, downloading, using or installing the accompanying software product, please ensure to read and accept the terms applying to this offering:

[LIMITED USE LICENSE AGREEMENT FOR DOCKER IMAGES FROM CUMULOCITY GMBH](https://cumulocity.com/docs/legal-notices/limited-use-license-for-docker/)

These tools are provided as-is and without warranty or support. They do not constitute part of the Cumulocity products. Users are free to use, fork and modify them, subject to the license agreement. While Cumulocity welcomes contributions, we cannot guarantee to include every contribution in the main project.

## License
   Copyright 2025-present Cumulocity GmbH

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF) ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

## Questions
Ask questions at https://techcommunity.cumulocity.com/tag/streaming-analytics-apama.
