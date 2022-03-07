# Generate CRDs tip


Issue with CRDs exist - https://github.com/argoproj/argo-cd/issues/820
Deployment splitted to CRDs deployment and helm chart deployment without CRDs

```
helm template prometheus-community/kube-prometheus-stack --include-crds --output-dir .
cp kube-prometheus-stack/crds/* crds/
```
