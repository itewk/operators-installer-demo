# operators-installer-demo

A place to start when testing the [operators-installer helm chart](https://github.com/redhat-cop/helm-charts/tree/master/charts/operators-installer).

## prerequisites

* admin access to an openshift cluster
* oc
* helm
* kustomize

## kickstart the gitops loop

1. download this repo
2. cd into this repo
3. log into your openshift cluster
4. install OpenShift GitOps Operator

        oc kustomize openshift-gitops-operator/overlays/management --enable-helm | oc apply -f -

5. configure OpenShift GitOps Operator

        oc kustomize openshift-gitops/overlays/management --enable-helm | oc apply -f -
