# Sample repository template for Cumulocity Streaming Analytics (Apama) applications

This repo provides a template for developing Cumulocity Streaming Analytics assets such as Blocks and EPL Apps, with a dev container for opening them in Visual Studio Code or GitHub Codespaces. 

If you're building your own EPL apps or Analytics Builder Blocks and want to store them in a GitHub repository, copying this template provides a great starting point for your own repository. 

This template contains an Apama project that is already configured with the required bundles, an Apama `.gitignore` file, and placeholders to show where you could put your own blocks, EPL apps and tests. It also includes a [Development Container](https://containers.dev/overview) configuration for quickly getting started using either [Microsoft Visual Studio Code](https://code.visualstudio.com/docs/devcontainers/containers) or [GitHub Codespaces](https://github.com/features/codespaces). 

If you are using the development container, the latest version of the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) and [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools) repositories are automatically available (in the parent of the parent directory of this repository, e.g. `myrepo/../../apama-analytics-builder-block-sdk`). If not, you need to clone those repositories yourself in that location. If you only doing EPL apps or block development but not both, you can delete the test and sample directories you are not interested in. 

The main branch of this repository is for the current cloud version of Streaming Analytics (currently 26.x).

### Getting started

Getting started is easy - just go to GitHub and select "Use this template". 

To work on your code locally, create a new repository from this template, then open it in Microsoft Visual Studio code by entering `Dev Containers: Clone Repository in Container Volume` into the command palette (`F1`) and then providing the HTTPS address of your repository. For details, follow the getting started instructions at https://marketplace.visualstudio.com/items?itemName=ApamaCommunity.apama-extensions. You can try out your blocks and apps using the PySys testcases under the `tests/` directory.

Alternatively, GitHub provides an option to immediately start working with the template using a codespace (if this is enabled by your GitHub administrator). You will need to wait for it to build the codespace, and then a little longer for it to load the extensions before you will see the syntax highlighting and other assistance features enabled. 

For more samples (and sample testcases) for working with Blocks and EPL Apps, see the [Block SDK](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) and [EPL Apps Tools](https://github.com/Cumulocity-IoT/apama-eplapps-tools) repositories.

If you already have an **existing Git repository** for your project, you can copy the `.devcontainer` directory from this template into it to add Dev Container support. You may also wish to copy the `.project` and `.dependencies` files from this template, especially if you don't already have an Apama project in your repository, or if you're using the Block SDK and EPL Apps Tools (since the relative path where they are present in the container may be different to where your current project looks for them). 

### Keeping up to date

You should regularly update your Apama installation, SDKs and OS packages to ensure you have the latest fixes, security updates and features. 

When using the dev container approach in VS Code, you can do this by running `Dev Containers: Rebuild Container` from the Command Palette (`F1`). This will wipe everything in the container, but not the workspace directory containing your project. If you are not using containers, you need to manually keep everything updated using both OS commands (e.g. `apt`) and `git pull` (for the SDKs). 

### Cumulocity cloud credentials
You need to provide the URL and credentials for your Cumulocity tenant so that PySys can access it. 

A convenient way to do this is to edit the `c8y-vars` script in this repository to set the Cumulocity URL and username environment variables required for your tenant. 

Then whenever you open a new shell you get started quickly by running `source c8y-vars` to set these environment variables, and also prompt you to paste in your Cumulocity password (for example, using your favourite password manager application). Feel free to customize the script for your needs - but for security reasons be sure not to commit any passwords into version control. 

### Advanced: customizing the Dev Container
If needed you can adjust some of the values within `.devcontainer/devcontainer.json` to use different base images and versions of the SDKs:

| Parameter                             | Description                                               | Comments                                      |
| -------------                         |:-------------:                                            | -----:                                        |
| APAMA_IMAGE                           | The base image containing Apama                           | The default is `apama-builder`. Please see [Amazon ECR](https://gallery.ecr.aws/apama) for available images. Note: the Dockerfile on this version of the branch is only compatible with Debian-based images. | 
| APAMA_VERSION                         | The tag of the Apama base container                       | The default is `latest`. Please see [Amazon ECR](https://gallery.ecr.aws/apama/apama-builder) for available versions. Note: the Dockerfile on this version of the branch is only compatible with Debian-based images.  |
| APAMA_ANALYTICS_BUILDER_SDK_BRANCH    | The branch/version of the Analytics Builder SDK           | The default is `main`. Please see [Github](https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk) for the available branches  |
| APAMA_EPLAPPS_TOOLS_BRANCH            | The branch/version of the EPL Apps Tools SDK              | The default is `main`. Please see [Github](https://github.com/Cumulocity-IoT/apama-eplapps-tools) for the available branches  |

__*Note:*__ The SDKs need to be for the same release line as the Streaming Analytics release in the Cloud that you want to deploy to. 

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

Prior to executing a `docker pull` command, or otherwise downloading, using or installing any containers, please ensure to read and accept the terms applying to the docker images: [LIMITED USE LICENSE AGREEMENT FOR DOCKER IMAGES FROM CUMULOCITY GMBH](https://cumulocity.com/docs/legal-notices/limited-use-license-for-docker/)

## Questions
Ask questions at: https://techcommunity.cumulocity.com/tag/streaming-analytics-apama
