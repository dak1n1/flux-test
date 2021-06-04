# flux-test

This repo contains kubernetes manifests related to running the FluxCD demo at https://fluxcd.io/docs/get-started/

I wanted to see what kind of CRDs Flux generates, so I output them into the ./crds directory.

```
$ kubectl get crd
NAME                                         CREATED AT
alerts.notification.toolkit.fluxcd.io        2021-06-04T00:21:38Z
buckets.source.toolkit.fluxcd.io             2021-06-04T00:21:38Z
gitrepositories.source.toolkit.fluxcd.io     2021-06-04T00:21:38Z
helmcharts.source.toolkit.fluxcd.io          2021-06-04T00:21:38Z
helmreleases.helm.toolkit.fluxcd.io          2021-06-04T00:21:38Z
helmrepositories.source.toolkit.fluxcd.io    2021-06-04T00:21:38Z
kustomizations.kustomize.toolkit.fluxcd.io   2021-06-04T00:21:38Z
providers.notification.toolkit.fluxcd.io     2021-06-04T00:21:38Z
receivers.notification.toolkit.fluxcd.io     2021-06-04T00:21:38Z
```

During bootstrapping, flux installs some operators that help generate manifests using various CRs and templates.

```
$ kubectl get deployment -n flux-system
NAME                      READY   UP-TO-DATE   AVAILABLE   AGE
helm-controller           1/1     1            1           22m
kustomize-controller      1/1     1            1           22m
notification-controller   1/1     1            1           22m
source-controller         1/1     1            1           22m
```

This repo is just an initial exploration of what FluxCD installs on a cluster.
