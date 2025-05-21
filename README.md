# Sample repository template for your Cumulocity Streaming Analytics (Apama) applications

If you're building your own EPL apps or Analytics Builder Blocks and want to store them in a GitHub repository, copying this template provides a great starting point. 

It contains an Apama project that is already configured with the required bundles, an Apama `gitignore` file, and placeholders to show where you could put your own blocks, EPL apps and tests. It also includes a [Development Container](https://containers.dev/overview) configuration for quickly getting started using either [Microsoft Visual Studio Code](https://code.visualstudio.com/docs/devcontainers/containers) or [GitHub Codespaces](https://github.com/features/codespaces). 

If you are using the development container, the latest version of the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) and [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools) repositories are automatically available in the parent of the parent directory (e.g. `myrepo/../../apama-analytics-builder-block-sdk`) of this repository. If not, you need to clone those repositories yourself in that location. If you are not doing _both_ EPL apps and block development, you can delete the test and sample directories you are not interested in. 

The main branch of this repository is for the current cloud version of Streaming Analytics (currently 26.x).

### Getting started

Getting started is easy - just go to GitHub and select "Use this template". 

You can work on your repository locally by creating a new repository from this template, then using Microsoft Visual Studio code. For details, follow the getting started instructions at https://marketplace.visualstudio.com/items?itemName=ApamaCommunity.apama-extensions. You can either use the container directly, or open it directly (e.g. in WSL on Windows) by performing a `git clone` of this repository, with a clone of the Block SDK and EPL Apps Tools SDKs alongside it. Note: if using a container, you may find the default memory allocated by your containerization tool needs to be increased from the default. We advise having a minimum of 4GB of memory for local development. You can try out your blocks and apps using the PySys testcases under the `tests/` directory.

Alternatively, GitHub provides an option to immediately start working with the template using a codespace (if this is enabled by your GitHub administrator). You will need to wait a short time for the container to download, and then a little longer for it to load extensions such as Apama which provide syntax highlighting and other assistance features. 

For more samples (and sample testcases), see the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) and [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools) repositories.

### Keeping up to date

You should regularly update to the latest Apama installation, SDKs and OS packages to ensure you have the latest fixes, security updates and features. 

When using the dev container approach in VS Code, you can do this by running `Dev Containers: Rebuild Container` in the Command Palette (`F1`). This will wipe everything in the container, but not the workspace directory containing your project. If you are not using containers, you need to manually keep everything up to date using both OS commands (e.g. `apt`) and `git pull` (for the SDKs). 

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

### Advanced: customizing the Dev Container
If needed you can adjust some of the values within `.devcontainer/devcontainer.json` to use different base images and versions of the SDKs:

| Parameter                             | Description                                               | Comments                                      |
| -------------                         |:-------------:                                            | -----:                                        |
| APAMA_IMAGE                           | The Apama Docker image to use                             | Please see [Amazon ECR](https://gallery.ecr.aws/apama) for available images. Note: the Dockerfile on this version of the branch is only compatible with Debian-based images.  | 
| APAMA_VERSION                         | The tag of the Apama base container                       | Please see [Amazon ECR](https://gallery.ecr.aws/apama/apama-builder) for available versions. Note: the Dockerfile on this version of the branch is only compatible with Debian-based images.  |
| APAMA_ANALYTICS_BUILDER_SDK_BRANCH    | The branch/version of the Analytics Builder SDK           | Please see [Github](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) for the available branches  |
| APAMA_EPLAPPS_TOOLS_BRANCH            | The branch/version of the EPL Apps Tools SDK              | Please see [Github](https://github.com/Cumulocity-IoT/apama-eplapps-tools) for the available branches  |

__*Note:*__ The Analytics Builder SDK needs to be in the same version as the Apama in the Cloud when you want to deploy. 

## Legal notices
Copyright 2025-present Cumulocity GmbH

These tools are provided as-is and without warranty or support. They do not constitute part of the Cumulocity products. Users are free to use, fork and modify them, subject to the license agreement. While Cumulocity welcomes contributions, we cannot guarantee to include every contribution in the main project.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Prior to executing a `docker pull` command, or otherwise downloading, using or installing this, please ensure to read and accept the terms applying to the docker images: [LIMITED USE LICENSE AGREEMENT FOR DOCKER IMAGES FROM CUMULOCITY GMBH](https://cumulocity.com/docs/legal-notices/limited-use-license-for-docker/)

## Questions
Ask questions at: https://techcommunity.cumulocity.com/tag/streaming-analytics-apama
