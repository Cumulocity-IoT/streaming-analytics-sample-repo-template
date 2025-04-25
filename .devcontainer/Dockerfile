ARG APAMA_VERSION
ARG APAMA_IMAGE
FROM ${APAMA_IMAGE}:${APAMA_VERSION}

USER root
RUN microdnf install git tar -y

# The mount location.
RUN mkdir "/workspaces"
RUN chown apama "/workspaces"

USER apama 
WORKDIR "/workspaces"

# Check out Block SDK at the mount location.
RUN git clone https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk.git
ARG APAMA_ANALYTICS_BUILDER_SDK_BRANCH
WORKDIR "/workspaces/apama-analytics-builder-block-sdk"
RUN git checkout ${APAMA_ANALYTICS_BUILDER_SDK_BRANCH}

WORKDIR "/workspaces"

# Check out EPLApps Tools at the mount location.
RUN git clone https://github.com/Cumulocity-IoT/apama-eplapps-tools.git 
ARG APAMA_EPLAPPS_TOOLS_BRANCH
WORKDIR "/workspaces/apama-eplapps-tools"
RUN git checkout ${APAMA_EPLAPPS_TOOLS_BRANCH}


ENV SHELL=/bin/bash
