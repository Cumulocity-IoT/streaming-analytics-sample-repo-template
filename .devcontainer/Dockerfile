ARG APAMA_VERSION=latest
ARG APAMA_IMAGE=public.ecr.aws/apama/apama-builder
FROM ${APAMA_IMAGE}:${APAMA_VERSION}

ARG USERNAME=apama
ARG USER_UID=1000
ARG USER_GID=${USER_UID}

USER root
RUN apt update && apt install git tar -y

RUN groupmod --gid ${USER_GID} ${USERNAME} \
    && usermod --uid ${USER_UID} --gid ${USER_GID} ${USERNAME} -d "/home/${USERNAME}"

RUN mkdir "/workspaces" && chown -R ${USER_UID}:${USER_GID} "/workspaces" \
  && mkdir "/home/${USERNAME}" && chown -R ${USER_UID}:${USER_GID} "/home/${USERNAME}"

USER ${USERNAME}

# Clone the SDKs. We clone under the home dir because "/workspaces" gets overwritten by the mount
# (and devcontainer.json workspaceMount is not respected in many cases - https://github.com/microsoft/vscode-remote-release/issues/3034)
ARG APAMA_ANALYTICS_BUILDER_SDK_BRANCH=main
RUN git clone https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk.git --branch ${APAMA_ANALYTICS_BUILDER_SDK_BRANCH} /home/${USERNAME}/apama-analytics-builder-block-sdk

ARG APAMA_EPLAPPS_TOOLS_BRANCH=main
RUN git clone https://github.com/Cumulocity-IoT/apama-eplapps-tools.git /home/${USERNAME}/apama-eplapps-tools --branch ${APAMA_EPLAPPS_TOOLS_BRANCH}

# Link the SDKs to the root dir so we can find them from /workspaces/projectdir using a relative path
USER root
RUN ln -s /home/${USERNAME}/apama-analytics-builder-block-sdk /apama-analytics-builder-block-sdk \
  && ln -s /home/${USERNAME}/apama-eplapps-tools /apama-eplapps-tools

USER ${USERNAME}
WORKDIR "/workspaces"

ENV SHELL=/bin/bash
