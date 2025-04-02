ARG APAMA_VERSION
FROM public.ecr.aws/apama/apama-builder:${APAMA_VERSION}

USER root
RUN microdnf install git tar -y

USER apama 
ENV SHELL /bin/bash

WORKDIR "/home/apama"
RUN git clone https://github.com/Cumulocity-IoT/apama-analytics-builder-block-sdk.git
ARG APAMA_ANALYTICS_BUILDER_SDK_BRANCH
WORKDIR "/home/apama/apama-analytics-builder-block-sdk"
RUN git checkout ${APAMA_ANALYTICS_BUILDER_SDK_BRANCH}
WORKDIR "/home/apama"