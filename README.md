![la logo](https://user-images.githubusercontent.com/42839573/67322755-818e9400-f4df-11e9-97c1-388bf357353d.png)

### Linux Academy Course Repository
### Hands-On GitOps

This repository is a resource provided for Linux Academy students taking the hands-on GitIOps course.

## Setup

```bash
kubectl create namespace flux
export FLUX_FORWARD_NAMESPACE=flux
export GHUSER="ekirmayer"
fluxctl install \
--git-user=${GHUSER} \
--git-email=${GHUSER}@users.noreply.github.com \
--git-url=git@github.com:${GHUSER}/content-gitops \
--git-path=namespaces,workloads \
--namespace=flux | kubectl apply -f -

kubectl -n flux rollout status deployment/flux

# Obtain RSA Key
fluxctl identity --k8s-fwd-ns flux
```
