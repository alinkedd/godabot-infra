# History

## Registry secret

1. Create service account with read/write access to Artifact Registry

2. Create secret for registry in local cluster:

```sh
kubectl create secret docker-registry regcred \
  --docker-server=europe-central2-docker.pkg.dev \
  --docker-username=_json_key \
  --docker-email=external-cluster-creds@godabot.iam.gserviceaccount.com \
  --docker-password="$(cat /path/to/file/godabot-[your-hash].json)"
```

1. Use regcred in deployment/pods config files to pull images.

## Useful links

- [k8s docs on pulling images from private registry](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/)
- [GCR docs on pulling images from private registry](https://cloud.google.com/anthos/clusters/docs/multi-cloud/aws/how-to/private-registry)
