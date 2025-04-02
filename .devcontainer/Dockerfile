ARG APAMA_VERSION
FROM public.ecr.aws/apama/apama-builder:${APAMA_VERSION}

USER root
RUN microdnf install git tar -y

# The mount location.
RUN mkdir "/workspaces"
RUN chown apama "/workspaces"

# Check out Block SDK at the mount location.
USER apama 
WORKDIR "/workspaces"
RUN git clone https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk.git
ARG APAMA_ANALYTICS_BUILDER_SDK_BRANCH
WORKDIR "/workspaces/apama-analytics-builder-block-sdk"
RUN git checkout ${APAMA_ANALYTICS_BUILDER_SDK_BRANCH}

ENV SHELL=/bin/bash
