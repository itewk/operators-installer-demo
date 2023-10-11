# operators-installer-demo

A place to start when testing the [operators-installer helm chart](https://github.com/redhat-cop/helm-charts/tree/master/charts/operators-installer).

## prerequisites

* admin access to an openshift cluster (preferably clean empty fresh install)
* oc
* helm
* kustomize

## kickstart the gitops loop

Once you do this procedure then OpenShift GitOps (ArgoCD) will be applying all kustomize content under the `management` overlay against your cluster, including the install and configuration of OpenShift GitOps (ArgoCD). This can cause a bad feedback loop sometimes and it is not recommended in production to have argo installing itself, rather an outside ArgoCD or Red Hat Advanced Cluster Manager should do that. But that is all beyond the scope of this demo/test repo.

1. download this repo
2. cd into this repo
3. log into your openshift cluster
4. install OpenShift GitOps Operator

        oc kustomize openshift-gitops-operator/overlays/management --enable-helm | oc apply -f -

5. configure OpenShift GitOps Operator

        oc kustomize openshift-gitops/overlays/management --enable-helm | oc apply -f -
