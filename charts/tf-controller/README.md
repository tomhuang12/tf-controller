# Weave GitOps Terraform Controller

The Helm chart for Weave GitOps Terraform Controller

## Installation

Before using TF-controller, you have to install Flux by using either `flux install` or `flux bootstrap` command.
After that you can install TF-controller manually with Helm by:

```shell
# Add tf-controller helm repository
helm repo add tf-controller https://weaveworks.github.io/tf-controller/

# Install tf-controller
helm upgrade -i tf-controller tf-controller/tf-controller \
    --namespace flux-system
```

## Configuration

The following table lists the configurable parameters of the TF-controller chart and their default values.

| Parameter                                         | Default                                     | Description
| -----------------------------------------------   |---------------------------------------------| ---
| `image.repository`                                | `ghcr.io/weaveworks/tf-controller`          | Controller image repository
| `image.tag`                                       | `<VERSION>`                                 | Controller image tag
| `image.pullPolicy`                                | `IfNotPresent`                              | Controller image pull policy
| `image.pullSecret`                                | `None`                                      | Controller image pull secret
| `runner.image.repository`                         | `ghcr.io/weaveworks/tf-runner`              | Runner image repository
| `runner.image.tag`                                | `<VERSION>`                                 | Runner image tag
| `installCRDs`                                     | `true`                                      | If `true`, install CRDs as part of the helm installation
| `replicaCount`                                    | `1`                                         | Number of TF-Controller pods to deploy, more than one is not desirable.
| `concurrency`                                     | `1`                                         | Concurrency of the controller
| `logLevel`                                        | `info`                                      | Level of logging of the controller
| `resources.requests.cpu`                          | `200m`                                      | CPU resource requests for the TF-Controller deployment
| `resources.requests.memory`                       | `64Mi`                                      | Memory resource requests for the TF-Controller deployment
| `resources.limits.cpu`                            | `1000m`                                     | CPU/memory resource limits for the TF-Controller deployment
| `resources.limits.memory`                         | `1Gi`                                       | CPU/memory resource limits for the TF-Controller deployment
| `nodeSelector`                                    | `{}`                                        | Node Selector properties for the TF-Controller deployment
| `tolerations`                                     | `[]`                                        | Tolerations properties for the TF-Controller deployment
| `affinity`                                        | `{}`                                        | Affinity properties for the TF-Controller deployment
| `rbac.create`                                     | `true`                                      | If `true`, create and use RBAC resources
| `serviceAccount.create`                           | `true`                                      | If `true`, create a new service account
| `serviceAccount.name`                             | `tf-controller`                             | Service account to be used
| `serviceAccount.annotations`                      | ``                                          | Additional Service Account annotations
| `runner.serviceAccount.create`                    | `true`                                      | If `true`, create a new runner service account
| `runner.serviceAccount.name`                      | `tf-runner`                                 | Runner service account to be used
| `runner.serviceAccount.annotations`               | ``                                          | Additional runner service Account annotations
| `podAnnotations`                                  | `{}`                                        | Additional pod annotations
| `podSecurityContext`                              | `{}`                                        | Pod security context configurations
| `securityContext`                                 | `{}`                                        | Container security context configurations
