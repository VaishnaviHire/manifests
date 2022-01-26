# OpenShift Service Mesh

[OpenShift Service Mesh 2.x](https://docs.openshift.com/container-platform/4.7/service_mesh/v2x/ossm-about.html) is based on [Istio](https://istio.io/) project and adds a
transparent layer for integrating and managing traffic flow across services. This repo allows users to use OpenShift Service Mesh for running Kubeflow applications as an alternative to
upstream Istio.

### Folders
Since Service Mesh requires config changes in all applications, a new stack called
`openshift-managed` was introduced.

There is one main folder called `openshift-servicemesh` that adds all the required custom resources for Service Mesh.

### Installation

#### Prerequisites

Before adding applications KfDef, make sure you have Service Mesh operator installed.
KfDef defined in odh-manifests can be used to install the required operators. Wait untill
all the operators are installed successfully.

```
apiVersion: kfdef.apps.kubeflow.org/v1
kind: KfDef
metadata:
  name: smsubscriptions
  namespace: openshift-operators
spec:
  applications:
  - kustomizeConfig:
      repoRef:
        name: odh-manifests
        path: openshift-service-mesh/
    name: openshift-service-mesh
```

####  Installation of Kubeflow applications

To install Service Mesh controlplane and kubeflow applications use the example [KfDef](/distributions/kfdef/kfctl_openshift_servicemesh.yaml)