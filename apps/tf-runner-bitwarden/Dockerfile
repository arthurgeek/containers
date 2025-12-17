FROM hashicorp/terraform:1.14.3 as tf

FROM ghcr.io/weaveworks/tf-runner:main-6188e8dd

# renovate: datasource=npm depName=@bitwarden/cli versioning=npm
ARG BW_CLI_VERSION=2024.1.0

USER root

RUN apk add --no-cache npm && npm i -g @bitwarden/cli@${BW_CLI_VERSION}

COPY --from=tf /bin/terraform /usr/local/bin/terraform

RUN chmod +x /usr/local/bin/terraform

USER 65532:65532
