# Generate CRDs tips


Issue with CRDs exist - https://github.com/argoproj/argo-cd/issues/820
Deployment splitted to CRDs deployment and helm chart deployment without CRDs.
In order to prevent too large error use the following annotation in CRDs
`argocd.argoproj.io/sync-options: Replace=true` [See doc](https://argo-cd.readthedocs.io/en/stable/user-guide/sync-options/#replace-resource-instead-of-applying-changes)

Generate CRDs:
```
helm template prometheus-community/kube-prometheus-stack --include-crds --output-dir .
cp kube-prometheus-stack/crds/* crds/
```
