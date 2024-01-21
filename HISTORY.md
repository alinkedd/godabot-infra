# History

## Registry secret

1. Create service account with read/write access to Artifact Registry and get
   a key in `json` format:
2. Create secret for registry in local cluster:
   ```sh
   kubectl create secret docker-registry regcred \
     --docker-server=europe-central2-docker.pkg.dev \
     --docker-username=_json_key \
     --docker-email=external-cluster-creds@godabot.iam.gserviceaccount.com \
     --docker-password="$(cat /path/to/file/godabot-[your-hash].json)"
   ```
   Don't forget to remove key file after.
3. If you use config files, add `regcred` as `name` for `imagePullSecrets`
   field to them. Or if you use CLI, then create a deployment and patch it
   like this:
   ```sh
   kubectl patch deployment godabot-app -p '{"spec":{"template":{"spec":{"imagePullSecrets":[{"name":"regcred"}]}}}}'
   kubectl rollout restart deployment godabot-app
   ```

## Useful links

- [k8s docs on pulling images from private registry](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/)
- [GCR docs on pulling images from private registry](https://cloud.google.com/anthos/clusters/docs/multi-cloud/aws/how-to/private-registry)
