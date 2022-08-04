# GitOps - Team Demo

This repository represents and GitOps based repository that a "team" would use for managing their application workloads.

This repository contains a [VS Code Remote Container](https://code.visualstudio.com/docs/remote/containers) configuration that provides the following:

- Openshift CLI
- Helm CLI
- Flux CLI

To use it, follow the [Getting Started](https://code.visualstudio.com/docs/remote/containers#_getting-started) guide, and then you must provide a .devcontainer/.env file that sets the following environment variables:

> A template has been provided in .devcontainer/.env-template that you can copy and modify

- OPENSHIFT_SERVER - The OpenShift server URL
- OPENSHIFT_USER - The Openshift username with admin priveleges
- OPENSHIFT_PASSWORD - The password for the Openshift user

### Authenticate with Openshift

```
oc login --server=$OPENSHIFT_SERVER --username=$OPENSHIFT_USER --password=$OPENSHIFT_PASSWORD
```
