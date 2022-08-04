# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.238.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use ubuntu-22.04 or ubuntu-18.04 on local arm64/Apple Silicon): ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="jammy"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# Install Helm
RUN curl https://get.helm.sh/helm-v3.9.0-linux-386.tar.gz -o helm-v3.9.0-linux-386.tar.gz
RUN tar -zxvf helm-v3.9.0-linux-386.tar.gz
RUN mv linux-386/helm /usr/local/bin/helm
RUN rm -rf linux-386 && rm helm-v3.9.0-linux-386.tar.gz

# Install OC CLI
RUN curl https://downloads-openshift-console.apps.keyhole-ocp4.be1i.p1.openshiftapps.com/amd64/linux/oc.tar -o oc.tar
RUN tar -xvf oc.tar
RUN mv oc /usr/local/bin/oc
RUN rm oc.tar

# Install the Flux CLI w bash completion
RUN curl -s https://fluxcd.io/install.sh | sudo bash
# RUN ~/.bashrc command -v flux >/dev/null && . <(flux completion bash)

# Install the kubeseal CLI
RUN curl -L https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.18.0/kubeseal-0.18.0-linux-amd64.tar.gz -o kubeseal-0.18.0-linux-amd64.tar.gz
RUN tar -zxvf kubeseal-0.18.0-linux-amd64.tar.gz kubeseal
RUN mv kubeseal /usr/local/bin/kubeseal
RUN rm kubeseal-0.18.0-linux-amd64.tar.gz