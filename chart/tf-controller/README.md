# TF-controller for Flux

A Helm chart for tf-controller

## Installation

Before using TF-controller, you have to install Flux by using either `flux install` or `flux bootstrap` command.

## Configuration

The following tables lists the configurable parameters of the Flux chart and their default values.

| Parameter                                         | Default                                              | Description
| -----------------------------------------------   | ---------------------------------------------------- | ---
| `image.repository`                                | `ghcr.io/chanwit/tf-controller`                      | Image repository
| `image.tag`                                       | `<VERSION>`                                          | Image tag
| `image.pullPolicy`                                | `IfNotPresent`                                       | Image pull policy
| `image.pullSecret`                                | `None`                                               | Image pull secret
| `installCRDs`                                     | `true`                                               | If `true`, install CRDs as part of the helm installation
| `replicaCount`                                    | `1`                                                  | Number of TF-Controller pods to deploy, more than one is not desirable.
| `resources.requests.cpu`                          | `50m`                                                | CPU resource requests for the TF-Controller deployment
| `resources.requests.memory`                       | `64Mi`                                               | Memory resource requests for the TF-Controller deployment
| `resources.limits`                                | `None`                                               | CPU/memory resource limits for the TF-Controller deployment
| `nodeSelector`                                    | `{}`                                                 | Node Selector properties for the TF-Controller deployment
| `tolerations`                                     | `[]`                                                 | Tolerations properties for the TF-Controller deployment
| `affinity`                                        | `{}`                                                 | Affinity properties for the TF-Controller deployment
| `rbac.create`                                     | `true`                                               | If `true`, create and use RBAC resources
| `serviceAccount.create`                           | `true`                                               | If `true`, create a new service account
| `serviceAccount.name`                             | `flux`                                               | Service account to be used
| `serviceAccount.annotations`                      | ``                                                   | Additional Service Account annotations
| `podAnnotations`                                  | `{}`                                                 | Additional pod annotations
| `podSecurityContext`                              | `{}`                                                 | Pod security context configurations
| `securityContext`                                 | `{}`                                                 | Container security context configurations
