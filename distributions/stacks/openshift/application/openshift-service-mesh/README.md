# OpenShift Service Mesh

[OpenShift Service Mesh 2.x](https://docs.openshift.com/container-platform/4.7/service_mesh/v2x/ossm-about.html) is based on [Istio](https://istio.io/) project and adds a
transparent layer for integrating and managing traffic flow across services. This repo allows users to use OpenShift Service Mesh for running Kubeflow applications as an alternative to
upstream Istio.

### Folders
Since Service Mesh requires config changes in all applications, a new overlay called
`servicemesh` was introduced in all the required application in `openshift` stack.

There is one main folder called `openshift-servicemesh` that adds all the required custom resources for Service Mesh.

###  Installation of Kubeflow applications with Servicemesh

To install Service Mesh controlplane and kubeflow applications use the example [KfDef](/distributions/kfdef/kfctl_openshift_v1.3.0_servicemesh.yaml)